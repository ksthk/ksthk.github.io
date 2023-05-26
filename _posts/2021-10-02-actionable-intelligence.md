---
layout: post
title:  Actionable Intelligence
date:   2021-10-02 13:06:52
description: How to make Cyber Threat Intelligence work for you
tags: cti
categories: research-papers
thumbnail: assets/img/thumbnail_cti.jpg
related_posts: false
---
Cyber Threat Intelligence (CTI) produces evidence-based knowledge on cyber threats and their implications within their relevant context, including actionable advice. With the technical landmark of the APT-1 report in 2013, CTI took off and it has contributed to society (Bellingcat’s MH-17 investigation) and diplomacy (Joint EU Diplomatic Response to Malicious Cyber Activities).

By now every larger organisation incorporates CTI in some fashion to improve security decision-making and detection. In that sense we have all heard CTI is an activity rather than something you buy, but it is time- and labour-intensive. Most of us don’t have dedicated resources to build threat landscapes and assessments. How to produce actionable intelligence when time and resources are scarce? In a position paper [^1] on CTI we have pointed out the pitfalls of CTI, and in this article we provide some guidance on how to avoid them.

**Creating actionable intelligence**
Intelligence is mere information if it isn’t actionable. We need interpretation. Interpretation facilitates action and distinguishes intelligence from mere data. Interpretation takes the organisation’s context into account and makes it actionable and useful input for decision-making. While many industry entities promise to deliver accurate CTI off the shelf, these offerings only work as fancy blacklists without in-house interpretation. An organisation’s CTI function will usually cater towards various internal stakeholders, such as C-level executives, security operations, vulnerability management and IT/security architects. All of these have different contexts and different views on actionability. On the one hand, we almost drown in CTI given the volume of threat reports and indicators pushed through feeds daily. On the other hand, internal data remains mostly untapped as potential sources of CTI. Regardless of our individual CTI priorities, we suffer from information overload. How to deal with this?

**Actioning the Intelligence Cycle**
We are all familiar with the Intelligence Cycle as originally put out by the US Department of Defense. A common complaint is that it is too abstract to serve as a basis for a CTI practice. For this reason, we provide practical recommendations per phase of the Intelligence Cycle.

![The (Actionable) Intelligence Cycle](/assets/img/cycle.png)

**Planning and direction**
It’s easy to hoard a firehose of whatever data is available, free feeds or the daily stream of reports. This also is a sure-fire way to an expensive SIEM bill for your SOC, and cognitive overload for your analysts. Consider only collecting data against pre-set goals based on stakeholder requirements, optionally formally established and signed-off as (Priority) Intelligence Requirements. Examples are threats specific to network infrastructure components or unique to your organisation’s industry vertical, which may be collected via feeds or reports. In case you decide to procure data to fulfil one or more requirements, be aware that because of sharing agreements between different vendors, you could end up paying for the same intelligence twice [^2]. Inform yourself about the origin of data upfront. From what type of sensors is the data sourced, where are these located? How much data is unique proportionally to what you’re already collecting? What is its half-life according to the provider?

**Collection**
For collection, many think primarily of feeds, but the most popular OSINT feeds have been shown to have more than three weeks’ delay reporting IoCs and to be highly biased due to specific collection methods of the supplier [^3]. This implies that if you are collecting feeds as part of an early-warning strategy, the value of feeds is more limited than you think. Also the quality of commercial data has been questioned as vendors have very scarce coverage of the threats on which they focus [^4]. OSINT is still a viable option, but there is more than feeds. A Twitter scraper like Twint or a web scraper such as Scrapy can allow for more targeted and timely collection on specific ATT&CK techniques or CVEs that are a concern to your organisation.

**Processing and exploitation**
Most of the challenges with processing are technical, centring on parsing and manipulating technical data into a supported format, or separating signal from the noise you might get from scrapers used to collect data from social media and other internet sources. When catering to an SOC, ideally CTI is only fed into an SIEM after analysis. In practice, processing and exploitation is often automated aggregation, parsing and enrichment, which doesn’t receive much reconsideration. But this phase is key to maximising the success of your CTI effort if you think about the half-life of indicators to avoid false positives. Deprecation should be source- and indicator-dependent. Who was the reporting source? And where does the indicator point? If it is cloud infrastructure or a short-lived DGA domain, the half-life is generally shorter. When deciding about automatic deprecation based on half-life, also consider versioning. Are you able to roll back and assess impact in case automatic deletion goes awry?

>"Be aware of what we call the false negatives gap. You want to have an approximation of the parts of your threat landscape that aren’t visible to you"

**Analysis and production**
Analysis is the hardest nut to crack. Many are vocal in their opinions when it comes to analysis, but it is tough to give practical guidance as it is a custom in-house process. Many conference talks provide lip service to Structured Analytic Techniques, a concept from the Intelligence Community.

But don’t be fooled by using standard methodology, because recent research shows mixed evidence on the reduction of confirmation biases and even shows it may increase (!) judgment inconsistency and error [^5]. Whatever methodology you use, it needs to fit your organisation’s internal processes, asset landscape and response strategy. Whatever methodology you use doesn’t really matter, as long as it is applied consistently by analysts, as consistent output is central to methodology. This is a question of training, which also includes making analysts familiar with the asset landscape, infrastructure design and response processes.

For strategic analysis, be aware that many of the freely-available commercial reports are potentially useful, but are produced primarily for advertising purposes, which has been shown to introduce systemic bias [^6]. Bias is almost implicit in specific collection techniques, but it isn’t harmful per se. You can have bias work for you by employing it as a deliberate focus. Depending on your threat landscape, you might like to increase focus by prioritising or sunsetting biased sources.

If you like to use one parameter to determine whether to pivot further during analysis, look for prevalence. Many reports exist, but it is often unclear whether they are based on single events or already widespread. Based on this, you can look into other parameters such as targeting, victims and impact. Furthermore, be aware of what we call the false negatives gap. You want to have an approximation of the parts of your threat landscape that aren’t visible to you. We tend to focus on false and true positives in the raw data we collect, but also be aware of what you do not see and how this implicates your CTI, but also your alerting strategy. You might like to prioritise threat hunting efforts to focus on these indicator twilight zones.

**Dissemination and integration**
If you want your SIEM to function as the single pane of glass it is supposed to be, good analysis is critical prior to dissemination to avoid false positives or alert overload. Be especially careful with adding CTI to your Security Orchestration, Automation and Response (SOAR) solution. Make sure it is analysed properly, as due to an SOAR’s integration and automated workflow with other tools, these solutions are force multipliers of false positives. In this case, running simulation tests with actual CTI datasets makes even more sense.

For dissemination of CTI to external partners, research proves what most of us observe in practice: sharing is scaring. The transaction cost of engaging, establishing quality and accuracy of shared data and risks of violating privacy and anti-trust laws are common barriers [^7]. This where the primary indicator of successful participation in sharing is perceived value and reciprocity belief [^8]. Privacy-enhancing technology such as zero-knowledge proof can however serve as an enabling solution to these issues.

**Evaluation and feedback**

This final step is a cost-benefit analysis that also evaluates how to increase the benefits. The total cost of ownership (TCO) of CTI must be compared against the return on investment (ROI) of efforts such as a Threat Intelligence Platform (TIP) and commercial feeds. Just like security in general, CTI is an insurance policy against bad stuff. Though quantifying its returns can prove challenging, reduction of Mean Time To Detect (MTTD), Mean Time to Respond (MTTR) and overall dwell time can serve as parameters here.

On a daily basis, the Key Performance Indicator (KPI) of strategic CTI efforts is whether it influenced or helped with the decision at hand. For IoCs, this a question of true-/false-positive ratio. Expensive commercial feeds have a higher TCO than OSINT feeds, thus they should be judged differently. If OSINT is the meat and potatoes, commercial feeds must be the cream of the crop. Their cost can be justified by their focus on actors and TTPs that matter to you specifically. If they don’t, consider what their added value is. At the end of the day, talking with industry partners and competitors is still free. Potentially high transaction costs mean it is not cheap, but it can yield highly relevant results.

On [our lab’s Publications page](https://www.cyber-threat-intelligence.com/publications/), full versions of other CTI-related work can be found.

_This article was originally published in [One Magazine 2021](https://emagazine.one-conference.nl/2021/actionable-intelligence-how-to-make-cyber-threat-intelligence-work-for-you/)_

[^1]: https://doi.org/10.1080/08850607.2020.1780062
[^2]: https://academic.oup.com/cybersecurity/article/4/1/tyy008/5245383
[^3]: https://www.cyber-threat-intelligence.com/publications/ACNS2019-feedtimelineness.pdf
[^4]: https://www.usenix.org/conference/usenixsecurity20/presentation/bouwman
[^5]: https://onlinelibrary.wiley.com/doi/full/10.1002/acp.3550
[^6]: https://www.tandfonline.com/doi/full/10.1080/19331681.2020.1776658
[^7]: https://dl.acm.org/doi/abs/10.1145/3339252.3340528
[^8]: https://www.sciencedirect.com/science/article/pii/S074756322030011X#sec5