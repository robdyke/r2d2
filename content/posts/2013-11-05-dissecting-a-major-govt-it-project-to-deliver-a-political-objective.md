---
authors: ["robdyke"]
date: "2013-11-05T17:49:50Z"
dsq_thread_id:
- 4390534143
guid: http://robdyke.com/rdb/?p=1100
id: 1100
tags:
- healthcare.gov
- hscic
- ukgovit
title: dissecting a major Govt IT project to deliver a political objective
url: /2013/11/05/dissecting-a-major-govt-it-project-to-deliver-a-political-objective/
---
Some notes taken on observing people the other side of the pond dissecting a major Govt IT project to deliver a political objective.

Would this project have benefited from [Opensorcery](http://www.businessweek.com/articles/2013-10-16/open-source-everything-the-moral-of-the-healthcare-dot-gov-debacle)? If PPACA wasn't communist enough! Writing in Bloomberg Businessweek, Paul Ford explains that the debacle known as [healthcare.gov](https://www.healthcare.gov/) makes clear that it is time for government to change the way it delivers IT: embrace the open source approach to software development that has revolutionized the technology industry. Well, openness worked before for Obama e.g. with the [IT spending dashboard](https://www.itdashboard.gov/) ([code here](http://sourceforge.net/projects/it-dashboard/)) but that was in the first years of the first term. You can do **anything** in that period of a presidency.

Looking at the Congressional hearing (which makes our [PAC look rather tame on NPfIT](http://www.publications.parliament.uk/pa/cm201314/cmselect/cmpubacc/294/29402.htm)) as [reported by Grauniad](http://www.theguardian.com/world/2013/oct/24/obamacare-website-testify-congress-live) two lessons stand out for me. One technical, the other political.

From a technical perspective the importance of proving an end-to-end test FIRST and n[ot two weeks prior to a go-live](https://twitter.com/SuzyKhimm/statuses/393392886965747712) is crucial. This is the approach we are taking with Wardware and the other projects we are working on. Can we pass a simple message through the components of the stack? No. Fix it. And now? Yes. Great! Build on and test for regressions.

<!--more-->

From a political perspective, it looks like this project was deliberately frustrated and suffered from a generally hostile atmosphere in Washington surrounding the ACA. This all but guaranteed that healthCare.gov would be late, broken, or both: "_As late as the last week of September, officials were still changing features of the Web site._" reports the Guardian. Many government IT projects, particularly ones that are created as the result of specific legislation - Choose and Book any one? the NHS Spine ensemble? - require the construction of an entirely new infrastructure. New needs careful planning, development, implementation and testing. It will break under the weight of continuous interruption and feature-creep. healthcare.gov was practically strangled by politicians ... the same people that are now apportioning blame via the helpful method of circular firing squad.

Then a week or so ago the single-point-of-failure did just that.

<img class="aligncenter size-medium wp-image-1124" alt="healthcare-error-640x426" src="/pubfiles/2013/11/healthcare-error-640x426-300x199.jpg" width="300" height="199" />

Over on Arstechnica Sean Gallagher gives his view on Obamacare site's litany of woes in a piece ['The seven deadly sins of HealthCare.gov'](http://arstechnica.com/information-technology/2013/10/the-seven-deadly-sins-of-healthcare-gov/): Hyper-complexity, Dependency issues, All-new build, Rolling requirements, Anti-testing, Release late & release once, Anti-bugfixing.

Thankfully NHS England & HSCIC are not looking like going down the same path - one previously well trod by UK Govt IT. The recently shared (in DRAFT) Strategy for the Health and Social Care Information Centre 2013-15 [[attached as PDF]](/pubfiles/2013/11/4a.-FINAL-For-Board-meeting-HSCIC-strategy.pdf) shows the changes in procurement and delivery of technology solutions to policy objectives.

"[HSCICs] future relationship with the market involves:"

<div>
  <ul>
    <li>
      Contracts with smaller financial values, covering shorter duration;
    </li>
    <li>
      Significant reductions in procurement timescales;
    </li>
    <li>
      Increasing use of Government frameworks;
    </li>
    <li>
      New approaches to engaging and driving the market, with particular emphasis on engaging with Small to Medium Enterprises and creating competitive market tensions not only during procurement, but throughout the delivery of a service;
    </li>
    <li>
      Less reliance on multi-national operators acting as prime contractors;
    </li>
    <li>
      Where possible leveraging services from other Government departments.
    </li>
  </ul>
  
  <p>
    I'm looking forward to the launches of e-Referrals / Customer Service Platform ... I'm not expecting a #fail.
  </p>
</div>