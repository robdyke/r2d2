---
authors: ["robdyke"]
date: 2021-03-29T00:20:32+01:00
#tags:
title: Responsible Rob
url: /2021/03/29/responsible
description: 🐧TL;DR. I found secret info on github, notified the owner and was thanked.<br/>When lawyers got involved my internet family supported me. <br/> Here's the story.🐧
---
Late February I discovered a public repository on github. The repo had a similar name to an Organisation I follow but I didn't recognise the Author. Intrigued, I forked the repo and cloned it. I took a look at the `git log`. There were approximately 2 years of commits from three authors to two branches (`master` and `◼️◼️◼️◼️◼️◼️◼️◼️`). Although I didn't recognise the github user that published the repo, the email address of the Authors were familiar.

I skimmed through the code. It looked like a portal app for business financial management built with Laravel. There were Views for purchasing, receipting, budgets and expenditure. Along with the code there was a compressed database dump which had that contained everything that shouldn't be posted to the internet: usernames, passwords (hashed), email addresses and API keys. 

> Now, raise your hand if you've never done this. I don't believe you. We've all made mistakes like this. When this happens you need to **quickly** invalidate the passwords or API keys that have been exposed to the public. Why? Your reputation, the reputation of your project or Organisation, and MOST IMPORTANTLY the security of your users and data is at stake.

There 





<div align=center>

<h2>The Apperta Foundation had a public repo on Github stuffed with secrets</h2>

</div>

When NHS England created [Apperta](https://apperta.org/) and gave it £500k to support open source projects, NHS England's Open Source Programme manager said:
Apperta would:

<p align=center><i>'be fully transparent, with information published online regarding where money has come from and where it has gone.'</i></p>

I don't think this was what was in mind.

As Apperta made a grant to NHSbuntu/NHoS of £40k grant back in 2017, I figured I'd assist them by providing as much information as possible about what looked to be a security breach / data leak.

![](/responsible/2021-03-22-23-12-53.png)



