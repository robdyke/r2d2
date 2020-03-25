---
author: Rob Dyke
date: "2011-04-24T15:55:24Z"
dsq_thread_id:
- 3878425641
excerpt: After much fruitless searching for helpful documentation to assist me in
  setting up the VPN services on a Cisco RV 120W to work with the open source client
  from Shrew Soft, I thought I'd better make a post here to help others.
guid: http://www.robdyke.com/noc/?p=456
categories:
  - No Overall Control
id: 456
tags:
- cisco
- open source
- technology
- vpn
title: Using Shrew Soft VPN client with a Cisco RV 120W
url: /2011/04/24/using-shrew-soft-vpn-client-with-a-cisco-rv-120w/
---
After much fruitless searching for helpful documentation to assist me in setting up the VPN services on a [Cisco RV 120W](http://www.cisco.com/en/US/products/ps10852/index.html) to work with the open source client from [Shrew Soft](http://www.shrew.net/), I thought I'd better make a post here to help others.

I'm setting up the VPN to use xauth (usernames and passwords) to authenticate sessions. I want to allow DNS/WINS through the VPN tunnel and I want to allow 'split tunnelling' so that internet access still functions while the tunnel is up.

I found a very helpful PDF guide to getting the Cisco device configured from [After much fruitless searching for helpful documentation to assist me in setting up the VPN services on a [Cisco RV 120W](http://www.cisco.com/en/US/products/ps10852/index.html) to work with the open source client from [Shrew Soft](http://www.shrew.net/), I thought I'd better make a post here to help others.

I'm setting up the VPN to use xauth (usernames and passwords) to authenticate sessions. I want to allow DNS/WINS through the VPN tunnel and I want to allow 'split tunnelling' so that internet access still functions while the tunnel is up.

I found a very helpful PDF guide to getting the Cisco device configured from](http://www.thegreenbow.com/) who produce VPN client software. The PDF for that guide is [here](http://www.thegreenbow.com/doc/tgbvpn_cg-cisco-rv-120w-en.pdf).

I also found a PDF guide written by Cisco to getting the [Shrew Soft client to talk to a Cisco SA 500](https://csc-prod1.cisco.com/docs/DOC-9378). There is another technote on configuring the [SA500 to accept the connections from a Shrew Soft client](http://www.cisco.com/en/US/docs/security/multi_function_security/multi_function_security_appliance/sa_500/technote/note/SA500_sshrew_technote.pdf) too, which is quite helpful.

Read on for the recipe.

<!--more-->

The Cisco RV120W is configured as per the GreenBow documentation. This is a very basic configuration, utilising the defaults wherever possible. The GreenBow instructions make use of a User FQDN, or User-specified Fully Qualified Domain Name, which can be a bit confusing on first read, and further confusing when it comes to setting up the client applications. I made a reference grid to help with the configuration.

<table border="0" cellpadding="0" cellspacing="0">
  <tr>
    <td class="configH2" colspan="3">
      Cisco RV120 VPN Router and ShrewSoft client Values for IKE:
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      &nbsp;
    </td>
    
    <td class="configL3">
      Cisco RV120
    </td>
    
    <td class="configL3">
      Shrew Soft Client
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Exchange Mode:
    </td>
    
    <td class="configL3">
      Aggressive
    </td>
    
    <td class="configL3">
      Aggressive
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      ID Type:
    </td>
    
    <td class="configL3">
      FQDN
    </td>
    
    <td class="configL3">
      FQDN
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Local WAN ID:
    </td>
    
    <td class="configL3">
      local.com
    </td>
    
    <td class="configL3">
      remote.com
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Remote WAN ID:
    </td>
    
    <td class="configL3">
      remote.com
    </td>
    
    <td class="configL3">
      local.com
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Encryption Algorithm:
    </td>
    
    <td class="configL3">
      3DES
    </td>
    
    <td class="configL3">
      3DES
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Authentication Algorithm:
    </td>
    
    <td class="configL3">
      SHA-1
    </td>
    
    <td class="configL3">
      SHA-1
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Authentication Method:
    </td>
    
    <td class="configL3">
      Pre-Shared Key
    </td>
    
    <td class="configL3">
      Pre-Shared Key
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Key-Group:
    </td>
    
    <td class="configL3">
      DH-Group 2 (1024 Bit)
    </td>
    
    <td class="configL3">
      DH-Group 2 (1024 Bit)
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Lifetime:
    </td>
    
    <td class="configL3">
      8 Hours
    </td>
    
    <td class="configL3">
      8 Hours
    </td>
  </tr>
  
  <tr>
    <td class="configH2" colspan="3">
      Cisco RV120 VPN Router and ShrewSoft client Values for VPN
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Encryption Algorithm:
    </td>
    
    <td class="configL3">
      3DES
    </td>
    
    <td class="configL3">
      3DES
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Authentication Algorithm:
    </td>
    
    <td class="configL3">
      SHA-1
    </td>
    
    <td class="configL3">
      SHA-1
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      Lifetime:
    </td>
    
    <td class="configL3">
      1 Hours
    </td>
    
    <td class="configL3">
      1 Hours
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      PFS Key Group:
    </td>
    
    <td class="configL3">
      DH-Group 2 (1024 Bit)
    </td>
    
    <td class="configL3">
      DH-Group 2 (1024 Bit)
    </td>
  </tr>
  
  <tr>
    <td class="configL1">
      NETBIOS:
    </td>
    
    <td class="configL3">
      Disabled (RV120)
    </td>
    
    <td class="configL3">
      Disabled (ShrewSoft)
    </td>
  </tr>
</table>

After configuring the Cisco RV120 as per the GreenBox documentation, I moved on to the ShrewSoft VPN Client. I've captured each of the screens for the setup. The key setup points to watch are the settings for Local and Remote, as Local is the client and remote is the Cisco. The other key settings to watch is the Network Topology setting on the last tab. You need to remember to add the network topology that you want your client to route to.

<div id='gallery-1' class='gallery galleryid-456 gallery-columns-3 gallery-size-thumbnail'>
  <dl class='gallery-item'>
    <dt class='gallery-icon portrait'>
      <a href='http://robdyke.com/rdb/2011/04/24/using-shrew-soft-vpn-client-with-a-cisco-rv-120w/ss1/'><img width="150" height="150" src="/pubfiles/2011/04/SS1-150x150.png" class="attachment-thumbnail" alt="SS1" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon portrait'>
      <a href='http://robdyke.com/rdb/2011/04/24/using-shrew-soft-vpn-client-with-a-cisco-rv-120w/ss2/'><img width="150" height="150" src="/pubfiles/2011/04/SS2-150x150.png" class="attachment-thumbnail" alt="SS2" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon portrait'>
      <a href='http://robdyke.com/rdb/2011/04/24/using-shrew-soft-vpn-client-with-a-cisco-rv-120w/ss3/'><img width="150" height="150" src="/pubfiles/2011/04/SS3-150x150.png" class="attachment-thumbnail" alt="SS3" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
  
  <dl class='gallery-item'>
    <dt class='gallery-icon portrait'>
      <a href='http://robdyke.com/rdb/2011/04/24/using-shrew-soft-vpn-client-with-a-cisco-rv-120w/ss4-remote/'><img width="150" height="150" src="/pubfiles/2011/04/SS4-remote-150x150.png" class="attachment-thumbnail" alt="SS4-remote" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon portrait'>
      <a href='http://robdyke.com/rdb/2011/04/24/using-shrew-soft-vpn-client-with-a-cisco-rv-120w/ss4-local/'><img width="150" height="150" src="/pubfiles/2011/04/SS4-local-150x150.png" class="attachment-thumbnail" alt="SS4-local" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon portrait'>
      <a href='http://robdyke.com/rdb/2011/04/24/using-shrew-soft-vpn-client-with-a-cisco-rv-120w/ss5/'><img width="150" height="150" src="/pubfiles/2011/04/SS5-150x150.png" class="attachment-thumbnail" alt="SS5" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
  
  <dl class='gallery-item'>
    <dt class='gallery-icon portrait'>
      <a href='http://robdyke.com/rdb/2011/04/24/using-shrew-soft-vpn-client-with-a-cisco-rv-120w/ss6/'><img width="150" height="150" src="/pubfiles/2011/04/SS6-150x150.png" class="attachment-thumbnail" alt="SS6" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon portrait'>
      <a href='http://robdyke.com/rdb/2011/04/24/using-shrew-soft-vpn-client-with-a-cisco-rv-120w/ss7/'><img width="150" height="150" src="/pubfiles/2011/04/SS7-150x150.png" class="attachment-thumbnail" alt="SS7" /></a>
    </dt>
  </dl>
  
  <br style='clear: both' />
</div>

Here is an [annotated ShrewSoft VPN client conf file](/pubfiles/2011/04/annotated-ShrewSoft-VPN-client-conf-file.txt) for reference.