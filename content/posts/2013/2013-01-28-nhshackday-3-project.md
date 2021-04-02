---
authors: ["robdyke"]
date: "2013-01-28T15:51:38Z"
title: NHSHackday 3 - Video consultations for healthcare
url: /2013/01/28/nhshackday-3-project/
tags:
- NHS Hackday
---
This weekend I was in Oxford for the first NHSHackday of 2013 where I worked on a video consultations project with some others from Tactix4 and [Alacrity Foundation](http://alacrityfoundation.co.uk/). I helped a few other with their hacking too, including [@amcunningham](https://twitter.com/amcunningham) and [@simon_penny](https://twitter.com/simon_penny) who created [Muto network](http://mutouk.org/).

We thought that as online appointment booking and using [video for clinical consultations are so QIPPing hot right now](http://www.connectingforhealth.nhs.uk/systemsandservices/qipp/library/index_html#skype-remote-consultations) with the NHS Commissioning Board and the Department of Health Tech Office falling over themselves to encourage the use of Skype for Doctor/Patient consultations and being loudly evangelical about appointment booking we ought to hack something for that.

Our view was that the use of Skype in healthcare has a few problems - it requires installs of software and a Microsoft account... And what about recording the consultation for 'training and quality purposes' or maybe embedding the video in the into the clinical record? These things are not possible with the current technologies the NHS uses (Skype, Cisco webex). Additionally video meeting software is not very 'accessible'; the tech usually excludes people who make use of screenreaders or other tech to make the interwebs accessible to them. Online booking is not widely adopted even though the GP systems and add-on products widely support this function.

Our hackday project enables browser based video consultations that are easily booked by a patient. We have tried to build a solution that would work with the established processes in a practice too, with the work flow of booking an appointment for an in-person consultation replicated for the video consultation.

<!-- iframe plugin v.3.0 wordpress.org/plugins/iframe/ -->

Choose and book: A patient chooses an appointment time from a list of slots published by the practice; the practice receptionist/administrator acknowledges and books the appointment; the clinician (Doctor / Practice Nurse) then holds the video consultation.

The consultation can include document sharing - e.g. for images of scans or PDFs of test results - as well as screensharing to allow for the clinical system to be viewed too. Additionally the entire conference can be recorded with the video stored for later retrieval by the patient and the clinician. We could even send the whole file as a coded-CDA document using NHS integration standards to another clinical system The opensource software we have used has lots of functions to support people with those specific accessibility needs needs.

There is still work to do on the project which we will continue in our [20% time](http://dilbert.com/strips/comic/2011-12-19/) over the coming weeks.