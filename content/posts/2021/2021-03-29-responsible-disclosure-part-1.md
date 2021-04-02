---
authors: [robdyke]
date: 2021-03-30
title: Responsible Disclosure - Part 1
description: "TL;DR. I found secret info on github, notified the owner, and found out the hard way that UK cyber law is broken. Part 1 of ...?"
slug: responsible-disclosure
categories: Disclosure
---
## How it started

Late February I discovered a public repository on github with a similar name to an Organisation I follow. Intrigued, I forked the repo and cloned it. I took a look at the `git log`. There were approximately 2 years of commits from three authors to two branches (`master` and `◼️◼️◼️◼️◼️◼️◼️◼️`). Although I didn't recognise the github user that published the repo, the email address of the Authors were familiar.

I skimmed through the code. It looked like a app for business financial management built with Laravel. There were Views for purchasing, receipting, budgets and expenditure. Along with the code there was a compressed database dump which had that contained everything that shouldn't be posted to the internet: usernames, passwords (hashed), email addresses and API keys. With the database you could get the app running local in a container. From the code you could work out where on the internet the app was running. Some of the Views included content loaded from a third-party site.

{{< center >}}
## The Apperta Foundation had a public repo on Github stuffed with secrets

{{< /center >}}

NHS England created [Apperta](https://apperta.org/) back in 2015 and gave it £500k to support open source projects. At the time NHS England's open source programme manager told [Digital Health News](https://www.digitalhealth.net/2015/06/open-source-super-cic-created/) that Apperta would:

> 'be fully transparent, with information published online regarding where money has come from and where it has gone.'

I don't think this was what was he in mind.

I know Apperta well. As Apperta made a grant to [NHSbuntu/NHoS](http://localhost:9081/2017/05/19/apperta-supports-nhsbuntu/) of £30k grant back in 2017, I figured I'd assist them by providing as much information as possible about what looked to be a security breach / data leak. I wrote up the discovery providing screenshots, URLs, and some notes about published vulnerabilities in the version of Laravel used. It looked something like this:

{{< center >}}

{{< figure src="/responsible/2021-03-22-23-12-53.png" width=400 caption="" >}}

{{< /center >}}

Here's the [gist](https://gist.github.com/robdyke/97bf14d00c3d01115fb6de4c8d185ce3) and a [PDF](/responsible/disclosure.pdf).

## Done

I sent the disclosure on 1st March at 12:12hrs. I received a reply with thanks at 12:46hrs.

Repos were taken down. The portal was taken offline.

All good.

## How it's going?

See part two...

