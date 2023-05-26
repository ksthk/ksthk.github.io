---
layout: post
title:  What's wrong with Cyber Threat Intelligence
date: 2020-07-14 13:03:20
description: Summary - Position Paper on the Challenges of the CTI Field
categories: research-papers
thumbnail: assets/img/thumbnail_cti2.jpg
---

Over the last decade the field of Cyber Threat Intelligence (CTI) has emerged, which aims to preempt cyber threats by combining aspects from Computer Science and the Intelligence field. Something like Risk Management, but less dusty, practical, operational and able to deal with a highly dynamic environment. Many former antivirus vendors have shifted gears to become commercial intelligence providers, conducting what is effectively counter intelligence analysis against cyber threat actors. As such, CTI has taken a significant role in daily cyber security practice.

Together with [Christian Doerr](https://www.cyber-threat-intelligence.com/people/christian), I have written a position paper arguing that CTI is a valuable addition to the cyber security field, but it is still in its infancy. Because of that, it often delivers flawed analysis. If you're a CTI analyst, you might argue this is all pretty obvious stuff, but it isn't. From a scientific perspective, most of our practice finds little empirical support and much of what we take as 'facts' is really not more than an opinion.

The paper was peer-reviewed by the International Journal of Intelligence and CounterIntelligence and has been published today. It is released as Open Access, so no annoying academic paywall and available to read [here](https://doi.org/10.1080/08850607.2020.1780062). It includes an overview of what CTI is, its origination and the challenges and potential it holds. As usual for a position paper, pointing out the field's challenges serves to identify areas for future research. CTI is rich in tools and technological knowledge, but poor on standardization and methodology. A better product follows a better process.

Below a quick rundown of the challenges identified in our analysis, which are discussed in more length in the [paper](https://doi.org/10.1080/08850607.2020.1780062):

* **CTI is lacking methodology:** Sherman Kent's [Analytic Doctrine](https://www.cia.gov/library/kent-center-occasional-papers/vol1no5.htm)[^1], Richards Heuer's [Psychology of Intelligence Analysis](https://www.cia.gov/library/center-for-the-study-of-intelligence/csi-publications/books-and-monographs/psychology-of-intelligence-analysis)[^2] and Structured Analytic Techniques[^3]. You've probably heard about them. Many conference presentations provide lip service to these works to indicate scientific rigor which really isn't there. Who does ACH in practice? Almost no-one. Actually, its effectiveness has proven to be [questionable](https://onlinelibrary.wiley.com/doi/abs/10.1002/acp.3550)[^4] at best.
* **CTI is shared but hardly being used:** we go into the relationship between the hacks of the Democratic National Committee and the German Bundestag and how this is actually a case of flawed CTI. Furthermore, we discuss the complications for sharing due to the Traffic Light Protocol and sharing communities such as ISACs.
* **CTI is generally of low quality:** indicator feeds report malicious activity months after the first observance and are biased towards specific countries. Most sharing takes place in the bottom of the [Pyramid of Pain](http://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html)[^5]. Complete TTPs are hard to share in a machine-readable way. Mitre ATT&CK is a first step in the right direction, but as a field we still need to progress significantly towards standardisation. We need to reach our full potential, or much of our initiatives will end up as yet another compliance effort providing limited value.
* **CTI vendors are untransparent in their supply:** do you know how your vendor gets to a certain assessment? How their raw intel was sourced? How their sensor base is distributed and thus potentially biased? Probably not. While sources do not need to be identified, it is currently unclear in many cases when a threat is novel or already has been reported on by another party under a different label. Vendor reports being more marketing material than actual intelligence doesn't help here.
* **CTI is too biased:** from a commercial perspective, vendors like to focus on the big state actors, which are actually a less likely threat for many of us than low-level cyber-criminal actors. The bulk of the vendor reporting focuses on a very small subset of threats which make for entertaining reading, but isn't very relevant to most of our daily practice.
* **CTI attribution is difficult:** Fancy Bear, APT-28, Sofacy, STRONTIUM, Sednit, Tsar Team, Swallowtail, Pawn Storm, TG-4127, Grizzly Steppe. Do you still follow this? These are all names for the same actor group. And while attribution is difficult and in many cases not more than a marketing stunt, which is a different ball game. Attribution should be left to government intelligence agencies.

Needless to say the above is a clickbaity representation of the more nuanced discussion in our paper, available for everyone [here](https://doi.org/10.1080/08850607.2020.1780062). For the [lab](https://cyber-threat-intelligence.com), this is where we hope to contribute with our research in the coming years. Because as indicated in the latter part of the paper, it isn't all that bad as the CTI field has already contributed much to cyber security and remains one of the most promising concepts for the years to come. Yet we improve through critical introspection and self-examination, not through praise and worship of established phenomenons.

![Bears all the way down](cozyfancybear.jpg)

[^1]:Davis, Jack. Sherman Kent and the profession of intelligence analysis. Central Intelligence Agency Washington DC, 2002.
[^2]:Heuer, Richards J. Psychology of intelligence analysis. Center for the Study of Intelligence, 1999.
[^3]:Heuer Jr, Richards J., Richards J. Heuer, and Randolph H. Pherson. Structured analytic techniques for intelligence analysis. Cq Press, 2010.
[^4]:Dhami, Mandeep K., Ian K. Belton, and David R. Mandel. "The “analysis of competing hypotheses” in intelligence analysis." Applied Cognitive Psychology 33.6 (2019): 1080-1090.
[^5]:Bianco, David. "The pyramid of pain." Enterprise Detection & Response (2013).