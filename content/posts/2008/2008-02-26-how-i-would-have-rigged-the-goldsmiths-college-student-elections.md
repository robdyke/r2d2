---
authors: ["robdyke"]
date: "2008-02-26T10:03:26Z"
categories:
  - No Overall Control
tags:
- Elections
- Goldsmiths
title: How I would have rigged the Goldsmiths College Student Elections...
---
How I would have rigged the Goldsmiths College Student Elections and some recommendations for the future.

There are many ways of rigging an election and, with increased abstraction and dispersal of the act of voting, influencing the outcome of ballots gets easier and easier.

Let's just think for a moment what takes place when a student votes. First of all, the student needs to be co-present with the ballot! This is a given and the only part of the process that can not be virtualised. The student presents some ID before being given a ballot paper. The ballot is privately completed and cast into the ballot box.

The Goldsmiths College Students Election e-Voting was extremely vulnerable to exploitation by someone with malicious intent. The e-voting mechanism virtualised the ballot paper instead of virtualising the whole process. Anyone visiting the goldsmithsstudents.com website was able to download a Microsoft Word file. This file used a macro to capture the input of the user; in this case the ranking of the preference of candidates. A student was expected to complete the form, save it, then send the file as an attachment from their college email account to <span class="Object" id="OBJ_PREFIX_DWT713">su@gold.ac.uk</span>

The most vulnerable part of the whole process is that **single file** made available for public download.

<!--more-->

It is possible to replace that single file on the web server with one containing a malicious modification to the macro which would be reported back to the returning officer. Here's how...

  1. Using social engineering and/or brute force gain administrative access to the oncampus server which hosts the goldsmithsstudents.com website as an administrator from goldsmiths.
  2. Download Word file
  3. Modify macro
  4. Upload modified Word file

After the e-voting period has ended, the intruder could gain access to the server again and replace the malicious file with the original. This would cover the tracks of the malicious intruder.
  
Part one is the tricky part, but with a mixture of social engineering (phone calls, distraction, impersonating &#038;tc) and automated (brute force) login attempts to the (publicly available) administration login, gaining this access is not impossible.

The beauty of this crack is two fold. Firstly, the file is replaced with an account that is legitimate and is therefore less likely to arouse suspicion. Secondly, the virtual ballot paper is rigged without anyone being able to spot it.

The one part of the GCSU e-voting process that seems sensible to me is the primate method of reducing fraudulent voting; by requiring the virtual ballot paper to be returned from a 'smiths college email account, some kind of verification of a ballot paper being sent in by a student is possible. However the act of sending the virtual ballot to a generic email address (<span class="Object" id="OBJ_PREFIX_DWT714">su@gold.ac.uk</span>) breaks one of the first principles I outlined: the sanctity of the secret ballot.

If the whole process had been virtualised the e-voting would have been a lot more secure. A secure webserver with authentication services provided by the college's directory server (as used for email and learn.gold for example) running a simple web ballot application would not have been open to a malicious attack of the type that I have just outlined. Sure, it would have had its own vulnerabilities but the code of the ballot process (the virtual paper) and the sanctity of the ballot booth (a goldsmiths webserver) would warrant greater confidence than the current model.

I'll be straight up and assure you that I've done no such thing; this is not some back-handed confession - you must be thinking it, right?

(The only hack I would like to do in these elections is increase participation, and participation is protected by the user sending an email from their college system account. Breaching this measure would require a significant and sustained attack on the goldsmiths college network. Besides, doubling the turnout would obviously arouse serious suspicions!)

So why tell you all this? Last week I read an article in computing magazine 2600 by Rop Gonggrijp 'What it means to be a hacker' [1] which called me back to my senses and my technology roots. The story was about electronic voting and the efforts of Dutch-German hacker communities to expose the significant and serious defects in the digitized ballot process. There have been other stories like this in America over the last 5 or 6 years [2].

One of the GCSU objectives for the period 2007/08 was to 'procure an effective e-voting system and integrate into Union elections'. This action is 'Owned' by James Hutchinson and was due to delivery in Nov '07.

So I've invited GCSU to comment. Have they procured an effective e-voting system? Have the Union done everything they can to insure the integrity of the e-voting process? Are the Sabbatical Officers confident in its integrity after reading this email? What can they do to ensure confidence in the privacy of the ballot?

[1] <span class="Object" id="OBJ_PREFIX_DWT715"><a target="_blank" href="http://blog.wired.com/sterling/2008/02/old-skool-hacki.html">http://blog.wired.com/sterling/2008/02/old-skool-hacki.html</a></span>
  
[2] <span class="Object" id="OBJ_PREFIX_DWT716"><a target="_blank" href="http://yro.slashdot.org/article.pl?sid=03/11/12/1320208">http://yro.slashdot.org/article.pl?sid=03/11/12/1320208</a></span> and many others, search terms slashdot e-voting in google
