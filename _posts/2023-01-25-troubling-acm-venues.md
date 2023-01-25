---
title: "Troubling ACM Venues"
excerpt: Citation fraud? In venues from reputable publishers? Oh my!
---

The Association for Computing Machinery, or ACM for short, is a well-known entity in computer science.
They provide resources for plenty of well-regarded scientific conferences and publish their proceedings,
in addition to other tasks such as organizing international programming contests and awarding the Turing Award, computer science's equivalent of a Nobel Prize.

Unfortunately, ACM appears too trusting of new conferences and too slow in reacting to problems. 

This post summarizes the problems I've found in ACM conferences organized by _[IARES](https://iares.net/)_,
the "_International Association of Researchers_". Most of their conferences are organized under ACM's banner, though some editions were organized with IEEE.
In particular, IARES includes two researchers evidently at the center of dubious activity: [Shadi Aljawarneh](https://dl.acm.org/profile/81456637051) from the Jordan University of Science and Technology,
and [Vangipuram Radhakrishna](https://dl.acm.org/profile/87658784457) from the Vallurupalli Nageswara Rao Vignana Jyothi Institute of Engineering and Technology.  
I summarize the problems below; curious readers can consult the [spreadsheet](https://docs.google.com/spreadsheets/d/1zui-mmVs_7NbDS-yTe1dtorQCAZ7YNjPaOoZ25q7BwE/edit?usp=sharing) with all details,
including links to [PubPeer](https://pubpeer.com/) comments for each problematic paper.

I did not originally intend for this to be a public blog post, as ACM has a form to report issues, but they did not even acknowledge my filling it for
[a conference](https://pubpeer.com/publications/30E8D340A91FA7A4AAEDF0AF4EF3B2) full of plagiarism, so here I am.


## Engineering and "MIS"

Let's first look at _ICEMIS_, the _International Conference on Engineering & MIS_.  
What's MIS? That is presumably left as an exercise for the reader, as it is not defined anywhere.
The [conference website](https://iares.net/Conference/ICEMIS2015) also suggests a hotel in _Morocco_ for a conference in _Turkey_, so perhaps explanations are not IARES's strong suit.  
Unlike many conferences, ICEMIS doesn't rotate its program chair: it's always Shadi Aljawarneh.

The 2015 edition is not that bad: it mostly contains papers that look like actual papers. There are already some cracks in the facade, though:
[a paper](https://doi.org/10.1145/2832987.2832992) consisting of one half-blank page, [a paper](https://doi.org/10.1145/2832987.2833042) in which Radhakrishna
cites himself 5 times without using these references in text, and [a paper](https://doi.org/10.1145/2832987.2833080) that does the same but not even from Radhakrishna himself.
If you think this is poor form, abandon all hope and read on.

The next edition of ICEMIS published by ACM is 2018. After this time skip, problems are more obvious.
There are 8 papers in which Aljawarneh or Radhakrishna make up more than 35% of the references.
For instance, [this one](https://doi.org/10.1145/3234698.3234735) boosted Radhakrishna's citation count by 26, in a paper with 34 references.
More worryingly, there are [1](https://pubpeer.com/publications/D159E7838FA657F776D4609A1F9C49), [2](https://pubpeer.com/publications/5127A4AFAA33F1406C669F6111611D),
[3](https://pubpeer.com/publications/D8983D3AD889E64A5E33933AF650F6) papers that cite Aljawarneh a few times in completely unrelated contexts, boosting his citation count for no apparent reason.
The peer review process also let some interesting oddities through, such as [a medical paper](https://doi.org/10.1145/3234698.3234750) that is clearly unrelated to the conference,
and [another medical paper](https://pubpeer.com/publications/CC3A9B757DDEA2F20922CC2CA78FB2) that is not only unrelated but also contains **verbatim plagiarism**.

ICEMIS 2019 makes the previous issues look subtle. The _[front matter](https://dl.acm.org/action/showFmPdf?doi=10.1145%2F3330431)_ contains over thirty citations to Aljawarneh.
[A paper](https://doi.org/10.1145/3330431.3330458) authored by both Aljawarneh and Radhakrishna cites them 31 and 40 times respectively, despite **not using any of its 70 references in the text**.
If you think that's bad, wait until you see [the one](https://doi.org/10.1145/3330431.3330460) with 77 references, 41 of which are to Radhakrishna, despite the paper being _less than one page of main text_ 
and not using any of the references either. There are 8 more papers that contain plenty of unused references to Aljawarneh and Radhakrishna.
[A user manual](https://pubpeer.com/publications/150E1C56DA17AD1E79059FCD903510) for a university's internal IT system even appears in there.

At this point, you may find it hard to believe it could get worse. You would be wrong. ICEMIS 2020 also cites dozens of papers in its front matter,
also contains citation vehicles for Shadi Aljawarneh, and for [1](http://web.archive.org/web/20230106223716/https://pubpeer.com/publications/8DC24BCCDA68EC1954E1FCA74FDB8E),
[2](http://web.archive.org/web/20230107131732/https://pubpeer.com/publications/3926A3A1554408CD7727379CFCD189), [3](http://web.archive.org/web/20230107134346/https://pubpeer.com/publications/A3D87B6A21E5BB27E5A32A85F6F1E0)
of them **authors have publicly denied inserting citations to the program chair**. ICEMIS 2021 also has the front matter problem _because its front matter editorial is a copy-paste of the 2020 edition_,
without even changing the dates. It also contains [1](https://pubpeer.com/publications/D0ACAAD32F23D42D1196B45A260406), [2](https://pubpeer.com/publications/DBBD091C274653EBF04FC75E8B4B0F),
[3](https://pubpeer.com/publications/0C7C1F371CB05161EEACC303692521) **papers that cite the program chair 113 times each**, using the same references list every time.
Two of these come from authors with the family name Aljawarneh, which is probably a complete coincidence.

Did ICEMIS even happen as a conference? Given that its [2020 edition](https://iares.net/Conference/ICEMIS20) supposedly happened starting September 14 in Kazakhstan,
a date on which the country was [under lockdown](https://kz.kursiv.media/2020-09-14/v-kazakhstane-oslabili-karantin/amp/) due to COVID and thus not in any state to host a public international event, one wonders.


## "Data"

IARES organizes another conference: _[DATA](https://dl.acm.org/doi/proceedings/10.1145/3279996)_, the ACM _International Conference on Data Science, E-learning and Information Systems_.
Once again, Shadi Aljawarneh is always program chair.

Do not confuse it with _[DATA](https://dl.acm.org/doi/proceedings/10.1145/3277868)_, the ACM _Workshop on Data Acquisition To Analysis_. Easy mistake to make; it's not like ACM could check their own event acronyms for uniqueness.

DATA follows the same pattern as ICEMIS: the 2018 edition starts as a mild citation vehicle for Radhakrishna, with 5 papers citing him unreasonably,
such as [this one](https://doi.org/10.1145/3279996.3280026) with 35 Radhakrishna references out of 44. In 2019, it gets worse, starting with the front matter which has the same reference list as ICEMIS 2019's,
and continuing with nearly a dozen papers that cite Aljawarneh in irrelevant contexts, such as [this one](https://pubpeer.com/publications/F10B0D57AEF6194643C923814547C0) that incremented his citation count by 18.

After a break, DATA 2021 was back and ready to get some science done… no, sorry, I meant ready to increase Vangipuram Radhakrishna's h-index, thanks to over a dozen papers citing him dozens of times each.
Take [this paper](https://pubpeer.com/publications/596E5E620475D4328A45B6F9E57508), for instance, which cites him 56 times for little effort, since its reference list is nearly the same as the one right before it in the proceedings.


## Conclusion

What's the morale of the story?

1. **Fraud can pay off**.
Shadi Aljawarneh has [6082 citations](https://scholar.google.com/citations?user=xm2Hp7YAAAAJ) and an h-index of 38 per Google Scholar,
above many well-regarded researchers. This probably helped him sit on the editorial board of [PeerJ](https://peerj.com/SJawarneh/) Computer Science, alongside well-regarded researchers.  
There are generally few consequences for research misconduct, [as Dorothy Bishop documented](http://deevybee.blogspot.com/2022/12/when-there-are-no-consequences-for.html).

2. **Fraud at this scale isn't hard to find if someone is looking**.
None of the problems I report above need special skill to find. These are not complex scientific issues, they are so basic that even skimming a paper sets off alarm bells.
Unfortunately, the sound of these bells apparently didn't bother big publishers, perhaps because they have few incentives to do anything about it.

3. **It is possible to automate at least some fraud detection!** Guillaume Cabanac's [Problematic Paper Screener](https://www.irit.fr/~Guillaume.Cabanac/problematic-paper-screener)
finds common issues in papers such as "tortured phrases", instances in which words have been replaced by synonyms to avoid plagiarism detection software,
often resulting in [unintentional hilarity](https://pubpeer.com/publications/059D502827972226591FC5F5421221).  
The Problematic Paper Screener is what flagged [an IARES paper](https://pubpeer.com/publications/55F9A59E75F052DB76CD5D58C0D786) in the first place and led to this work.  
There are currently 24 ACM papers flagged by the PPS as suspicious, plus 8 which cite papers themselves flagged as suspicious.

Sleuthing work like this can lead to retractions including for ACM, such as [this paper](https://doi.org/10.1145/3292425.3293461) which was flagged as being computer-generated,
or [this entire conference](https://dl.acm.org/doi/proceedings/10.1145/3292425) due to fraudulent peer review,
as documented [on RetractionWatch](https://retractionwatch.com/2022/04/20/more-than-300-at-once-publisher-retracts-entire-conference-proceedings/).

If the scientific community wishes to be taken seriously, we must set up incentives for publishers such as ACM to do at least basic checks of the texts they publish and the venues they sponsor.



_I would like to thank Steve Haroz, Kendra Albert, and Jannik Peters for their feedback, and Guillaume Cabanac for his Problematic Paper Screener and the community he has built around it._
