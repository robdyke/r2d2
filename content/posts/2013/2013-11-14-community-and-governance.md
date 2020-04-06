---
authors: ["robdyke"]
date: "2013-11-14T13:09:32Z"
dsq_thread_id:
- 4390534410
guid: http://robdyke.com/rdb/?p=1145
id: 1145
tags:
- CIC
- HSCIC
- Open Source
title: Community and Governance
url: /2013/11/14/community-and-governance/
---
This is the second in a short series of posts where I'm looking at the announcements from NHS England / HSCIC in support of open source solutions for NHS organisations. In this post I'm looking at the role of governance and community around open source projects.

Following the Safer Hospitals, Safer Wards Technology Fund announced in June of this year, [Gary McAllister posted a comment piece](http://garymcallisteronline.blogspot.co.uk/2013/07/open-source-in-nhs.html) which neatly summarises key criteria of open source which I paraphrase here:

  1. The code should be freely available online, well-documented and accessible. It should be evident from the code repository that regular commits are made to the project from multiple sources, demonstrating that the code-base is active.
  2. The licensing for the code should utilise an "Open" license. Examples of licenses which meet the Open Source Initiative definition of open source can be seen here.
  3. A project should have corporate investment and a viable service provider clearly backing the product. This may sound counter intuitive but in order for an Open solution to be viable long-term it needs backing from a corporate entity. Without corporate backing the solution is "unsupported" and there is little evidence to ensure continued development. You could end up with a stale loaf of bread.

<!--more-->

These are good criteria and should be foremost in the mind of NHS-E, HSCIC and other healthcare organisations when considering procuring solutions based on open source software or engaging in an open source software project as a development or domain expert partner or when releasing code developed in house to the wider healthcare economy.

As mentioned in my last post, none of this is particularily new to HSCIC, or rather, CfH as was then. The [eHealthOpenSource KTP project](http://www.ehealthopensource.com/about-us/ktp-project/) run out of CfH, Data Standards and Products and the Department of Health Informatics Directorate covered much of this ground in its few years of live. There are several pieces published on the eHos website by the project team which over in detail licensing and development approaches As an industry partner of the eHos KTP, Tactix4 supported the establishing of a code forge for CfH and NHS organisation code. See <http://forge.tactix4.net/gf/> The forge won a award for innovation from the NHS Innovation Centre and the Cabinet Office, not for its technology but for the initiative of supporting the publishing of code and for its part in helping to sustain a active developer community. After initial pump priming, it was envisaged that eHealthOpenSource would evolve into an independent and self-sustaining organisation. This hasn't happened as I outlined before, however the forge lives on and code continues to be committed by NHS organisations including HSCIC and Leeds Teaching Hospital. While eHos was somewhat successful in fulfilling criteria 1 and 2, it did not evolve into providing a corporate investment role although viable service providers around open source solutions have emerged.

### Risk.

After much <del>leaning on</del> encouragement to open source its PICS, it has been announced that University Hospitals Birmingham will offer its Prescribing Information and Communication System to the NHS not as open source but on a licence-free basis via some sort of escrow mechanism.

> The trust’s medical director, [Dr Dave Rosser, told EHI](http://www.ehi.co.uk/news/EHI/9028/birmingham-to-offer-pics-licence-free) that Birmingham would not be offering its PICS e-prescribing system open source because it is too risky. “We think open sourcing PICS would be dangerous. It’s too complicated a programme with very complicated code,” said Dr Rosser. “It would be risky to say the least. It has 600,000 lines of code and it is all interactive. It’s very easy to make a change in one part that changes something in another part that not even the programmers can predict.”

I feel that this mode of releasing software will actually undermine policy objectives ([as previously discussed](http://robdyke.com/2013/11/12/levelling-the-playing-field-educating-the-customer/)) and does a disservice to healthcare technology (open or otherwise....). Software needs governance and assurance. Escrowing code does not deliver these. This mode of publishing code gives nothing beyond a pile of soft spaghetti to the NHS: this is not a comment on the PICS solution which we know works for UHB ... and while I'm not advocating a partial->full re-factor of this obviously successful code base either, in order for others to adopt and deploy assurances are needed in the forms of:

  * Community. meaningful ways in which others can participate in the development (technical, functional, social, etc) of the project;
  * Testing. unit tests, code coverage and continuous deployment of the base to help with regression/development testing;
  * Documentation. you know, that stuff that tells people how it works;
  * Governance. an organisation (and I use the term loosely) that will assure, for example, ISB0129/0160 practices in place.

There are not small beer tasks. These four aspects are the sort of roles that OSEHRA perform for the VistA community and that the Apache Software Foundation perform for larger opensource projects. You can see how Apache incubate and onboard projects and codebases [here](http://incubator.apache.org/). Without the above four, then yes it is too risky for another organisation to adopt and implement the code, open source licensed or otherwise.

### Governance.

Where NHS-E have been discussing open source the role of corporate investment and of viable service partners to support and sustain such solutions has come up. EHI report this as '...the government will put in place safe guards in form of a custodial structure...to ensure that the open source software is used safely.'  To my mind, the reporting of open source in this way by EHI muddies the water. To use **any** software safely in a clinical environment the Information Standards Board has published [ISB0129](http://www.isb.nhs.uk/documents/isb-0129) and [ISB0160](http://www.isb.nhs.uk/documents/isb-0160) which cover the responsibilities on the supplier/developer of a software product and on the procuring/implementing organisation respectively. The full title of ISB 0129 is "Clinical Risk Management: its Application in the Manufacture of Health IT Systems". This guidance pertains to any software development where the intended use is a clinical setting, regardless of the license model that the code is published under. Also covering software development is the EU Medical Device Directive. The certification process is clear and it applies across Europe. This presentation from [Dr Neil Ebenezer at Medicines and Healthcare Products Regulatory Agency](https://www.dropbox.com/s/uq98szozu8b3im7/RSM%20April%202013-Final.pdf) gives a great overview to developing software for a clinical setting.

Back to Birmingham - EHI Live, not UHB - again where [Beverley Bryant told reporters](http://www.ehi.co.uk/news/ehi/9010/%C2%A320m-of-tech-fund-to-go-on-open-source):

> “What we propose is to create a structure of custodians,” adding “We haven’t finished the work in terms of the detail.”

Now, I wasn't at the key-notes given by Bryant or Kelsey or others from NHS-E as I was either presenting at HANDI Health or in the Open Source Skunkworks.

### Community? Interested!

In my session in the HANDI Health conference stream I illustrated an exemplar structure for a custodian organisation around open source projects. I advocated the use of Community Interest Companies to 'own' the code and to manage the governance of an open source project. This approach would be in line with the Foundation model around Apache or the OSEHRA organisation around VistA. I am not advocating one-organisation-to-rule-them-all and all the bloat and anti-innovation that comes with it; nor am I advocating a wild-west free-for-all. I advocate playing-nicely-with-others.

> A [Community Interest Company (CIC)](http://www.bis.gov.uk/cicregulator) is a limited company, with special additional features, created for the use of people who want to conduct a business or other activity for community benefit, and not purely for private advantage.

My full slides from the HANDI Health event have already been [posted to Slideshare](http://www.slideshare.net/robdyke/t4-ehi-handi-2013) and I've [blogged about the session here](/2013/11/09/handi-selfish-or-selfless-sorts-of-software-for-social-systems/).

I advocate CICs for a few reasons, mainly:

  * Obvious **Community** - NHS Organisations!
  * Shared **Interests** - in using IT to deliver clinical and business functions to staff;
  * Runs just like a **Company** - to help with the Cabinet Office / BIS agendas in support of UK Plc, SME, Wealth creation etc.

Here is a simple example of a CIC organisation for an open source project:

{{< figure alt="Simple CIC" src="/pubfiles/2013/11/Simple-CIC.png" width="651" height="389" >}}

Still with me at the back? Here is a more complex model showing how a CIC might operate as a business: managing partner relationships, releasing software, assuring regulatory compliance, &tc.

{{< figure alt="Complex CIC" src="/pubfiles/2013/11/Complex-CIC.png" width="640" height="401" >}}

This sort of approach would also work for an over-aching governance & assurance model for NHS-England / HSCIC to adopt. We could think of an NHS-E-CIC as a Big Tent in which a variety of organisations could become members and actively participate in the governance and assurance of healthcare IT _in general_ while at the same time leaving individual projects to decide for themselves appropriate approaches to the same.

Ideally we end up with [something like this](http://www.haneke.net/) ... only in pink.

Tactix4 are establishing a number of Community Interest Companies around the various open source projects that we are working in right now. There will announcements on the T4 website in due course.
