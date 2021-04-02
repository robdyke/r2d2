---
authors: ["robdyke"]
date: "2013-11-09T15:49:14Z"
tags:
- EHIlive 2013
- HANDI Health
- Open Source
title: My HANDI Health 'live coding' workshop.
url: /2013/11/09/my-handi-health-live-coding-workshop/
---
## The Village

This last week I was at EHI Live with HANDI and Tactix4. HANDI were producing one of the streams at this exhibition 'The HANDI Health Apps Conference'. HANDI Health Apps is the first national conference dedicated to health & social care apps and lightweight digital tools to take place in the UK.  It was a “must attend” event for app developers, health and care professionals, managers and commissioners who are seeking to understand how this new generation of digital tools can support the delivery of efficient, patient centred care. The conference included the HANDI-App Village located right in the centre of the EHI Live Exhibition providing a unique platform where health and care app developers can showcase their products without getting lost amongst the large stands of the major IT vendors.

And we had a village pub, serving real beer and excellent pork scratchings.

I thought it was a good idea to 'live code' an app. In hind sight it was a good idea to 'live code' an app and, except for the failure of the internet link, it would have worked well. Thankfully, as a child of Blue Peter, I had an app that I had made earlier prepared and ready installed on my device. With this APK file I was able to demo an app that scanned a barcode containing a URL and launch a browser. Here is the [APK](http://www.robdyke.com/WWScan-QR.apk) and here is the [QR code](http://www.robdyke.com/EhiLive.png).

<!--more-->

## 'Nice barcode - now what?'

I decided to code a simple barcode scanning app using freely available open source tools. The goal was to produce something simple that scanned a barcode (QR or GS1) and then opened a browser with the URL in the barcode. This would provide a base framework for a scan->web page app.

I decided to do the demo from my Linux Mint laptop. You could do all this on Windows or on a Mac. Instructions can be found all over the internet. You'd need an Apple machine to make an app for an iDevice.

#### Kit list:

  * [Node.js](http://nodejs.org/) and the [Node Package Manager](https://npmjs.org/)
  * [Cordova](http://cordova.apache.org/) : a set of device APIs that allow a mobile app developer to access native device function such as the camera or accelerometer from JavaScript. Combined with a UI framework such as jQuery Mobile or Dojo Mobile or Sencha Touch, this allows a smartphone app to be developed with just HTML, CSS, and JavaScript. [Phonegap](http://phonegap.com/) is a free and open source framework that allows you to create mobile apps using standardized web APIs for the platforms you care about. (developed by Adobe, now called Cordova and curated by Apache Foundation)
  * [Barcode scanner plugin](https://github.com/Scandit/BarcodeScannerPlugin) from Scandit (but you could use [BarCodeScanner](https://github.com/wildabeast/BarcodeScanner) plugin from [@wildabeast](https://github.com/wildabeast) who is one of the original phonegap developers)
  * [InAppBrowser](https://github.com/apache/cordova-plugin-inappbrowser) plugin
  * I also needed to install the Android Developer Tools and the Sun Java Development Kit

#### Method:

I decided to leave as out of scope the installation of the JDK and ADT dependencies. These are extensively covered [here](http://cordova.apache.org/docs/en/3.1.0/guide_platforms_android_index.md.html#Android%20Platform%20Guide). I also left as out of scope covering installing [node.js](http://nodejs.org/) and NPM (the [node package manager](https://npmjs.org/)).

From the command line, I installed cordova & plugman using npm

```sudo npm install cordova
sudo npm install plugman
```

I then created a new cordova project and added android platform features

```
cordova create ehiscan1 com.example.ehiscan1 EHIScan1
cordova platform add android
```

I downloaded the scandit plugin and unzipped it before installing it with plugman

```
plugman install --platform android --project /home/robdyke/Development/ehiscan1/platforms/android/ --plugin /home/robdyke/Downloads/scandit/
plugman install --platform android --project /home/robdyke/Development/ehiscan1/ --plugin org.apache.cordova.inappbrowser
```

#### Write some code:

Now to edit the index.html file to load the barcode scanner and perform an action on the input. I edited www/index.html and replaced everything between the body tags as follows:

```
body onload="onBodyLoad()" style="background: url(img/ScanditSDKDemo-Splash.png) no-repeat;background-size: 100%;background-color: #000000"&gt;
        &lt;script type="text/javascript" src="cordova.js"&gt;&lt;/script&gt;
        &lt;script type="text/javascript" src="js/index.js"&gt;&lt;/script&gt;
        &lt;script type="text/javascript"&gt;
            function onBodyLoad()
            {
                document.addEventListener("deviceready", onDeviceReady, false);
            }

	    function success(resultArray) {
	    	var barcode = resultArray[0];
	    	window.location = barcode;
            }

            function failure(error) {
                alert("Failed: " + error);
            }

            function scan() {
                cordova.exec(success, failure, "ScanditSDK", "scan",
                             ["YOUR API KEY HERE",
                              {"beep": true,
                              "1DScanning" : true,
                              "2DScanning" : true}]);
            }

            app.initialize();
            &lt;/script&gt;
        &lt;div align="center" valign="center"&gt;
            &lt;input type="button" value="scan" onclick="scan()" style="margin-top: 230px; width: 100px; height: 30px; font-size: 1em"/&gt;
        &lt;/div&gt;
    &lt;/body&gt;
```

This could clearly be improved ... as I'm really not a coder, your contributions welcome!

The key part of the code above is the section:

```
function success(resultArray) {
	    	var barcode = resultArray[0];
	    	window.location = barcode;
            }
```

This function takes the (resultArray) from a successful barcode scan and passes the value var from the scan to the in app browser for action, in this case opening it as a URL input.

#### Package:

The method for building and packaging an Android app from Cordova is well documented on the internet. I simply issued a cordova build command and then asked the Android SDK to package the code up and sign it for release.

#### Release:

I've put my code from this hack on github here <https://github.com/robdyke/handihealthhack1>
