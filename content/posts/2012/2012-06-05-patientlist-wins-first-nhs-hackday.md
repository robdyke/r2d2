---
authors: ["robdyke"]
date: "2012-06-05T13:56:37Z"
guid: http://www.tactix4.com/?p=594
id: 594
tags:
- NHS Hackday
- Open Source
title: PatientList wins first NHS Hackday
url: /2012/06/05/patientlist-wins-first-nhs-hackday/
---
I participated in the first [NHS Hackday](http://nhshackday.com/) last month. The weekend event in central London brought together doctors, healthcare leaders and software developers with the aim of creating solutions to problems experienced on a daily basis in the NHS.

The winning development, called ‘Patient List’, aimed to improve the handover of patients and replace the traditional task-list methods usually employed by doctors.

The Patient List problem is felt by every junior doctor in the NHS, but it was formally raised by Wai Keong Wong in a blog post titled ["Give every doctor an extra 30mins/day with patients](http://blog.openhealthcare.org.uk/?p=66) by solving the [‘Patient List’ problem](https://groups.google.com/forum/#!topic/nhshackday/8JAwPEQbJbk/discussion)". In summary, a system is needed to save junior doctors from error-prone manual daily work compiling lists of patients and their treatments for their daily rounds. Furthermore, the system should include task lists for each patient and a way to manage transfer of tasks between shifts and departments so that nothing gets forgotten during handover.

<!--more-->

I worked on a solution using HL7 data to populate a database. A dummy data set of patients, admissions, wards and consultants was reused from an open source project [Wardware](http://wardware.info/). [NewContext](http://www.newcontext.com/) and [ValueDecision](http://www.valuedecision.com/) teamed up with Dr Colin Brown at the Hack Day to develop a solution. The system created at the Hack Day has the following features.

  * Complete list of patient details available on demand
  * Lists can be filtered by ward
  * Patients can be marked as high, medium and low risk
  * To Do items can be assigned to a patient
  * To Do items can be marked as pending and then completed
  * A full history of To Do items is available for each patient
  * A real-time view on actions for patients and their state for any clinician

Here is the presentation we made:

And a video of our pitch