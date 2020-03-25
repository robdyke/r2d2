---
author: Rob Dyke
date: "2012-09-28T14:23:07Z"
dsq_thread_id:
- 3851494986
guid: http://www.tactix4.com/?p=602
id: 833
tags:
- NHS Hackday
- open source
title: AsKiT collaboration comes second at Liverpool NHS Hackday
url: /2012/09/28/askit-collaboration-comes-second-at-liverpool-nhs-hackday/
---
With the rest of Tactix4 I headed to Liverpool in September for the second NHS Hackday. We worked on a project called [AsKiT](http://wiki.nhshackday.com/wiki/AsKit) which came second. It was great to collaborate with others from NHS organisations to create problem solving code.

**The Problem: **All throughout the NHS there are a myriad of forms, questionnaires and assessments that need to be done, and the vast majority of them are done on paper, with the results stored in a folder in a cabinet or later scanned in and saved as a pdf file. Neither of these solutions allows ready access to the information in a digital form, and does not provide any of the benefits of digital capture.

**The Solution:** By creating a general-purpose question asking android app we have removed the need for the paper part of the process, now the questions are displayed on the screen and the results are captured digitally. It is no longer possible to write something that is illegible, or answers a numerical question with letters, or forget to answer certain questions. The results are then sent securely to the server where they are stored and can be forwarded directly to the appropriate system for further use.

<!--more-->

In addition to the app, there is a web based front end that can be used to generate new surveys, add scoring systems to weight the questions or branching for handling nested questions or if/then type interactions. This simple to use system is suitable for anyone to use, and can very quickly create a replacement for virtually any paper-based questionnaire or form.

**Features**

  * Easy to use web site for creating survey
  * Support for scoring of answers, e.g. Waterlow score.
  * Support for branching questions meaning only the relevant questions need to be answered
  * Version control so you are always answering the latest, most up to date version of the survey
  * Multiple question types e.g. Check box, Radio button, Free Text, Numerical, Stars, Sliders
  * Results can be submitted back to the server to be stored and further processed, e.g. emailing, PAS integration, EPR integration.
  * Lightweight front and back end are easily deployed on modest resources with zero configuration
  * Works on any Android device
  * Open Source, so can be branched and customised for use in specialised domains if needed

**The presentation:**

  
<!-- iframe plugin v.3.0 wordpress.org/plugins/iframe/ -->

**Source Code:**

  * <http://forge.tactix4.net/gf/project/askit/> The Android App Source Code
  * <http://forge.tactix4.net/gf/project/surveygen/> The Server Source Code

**The Developers:**

  * [Tactix4 team](http://www.tactix4.com/)
  * [iLINKS Innovations](http://www.ilinksinnovationsmersey.nhs.uk/)