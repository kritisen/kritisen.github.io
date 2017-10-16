---
layout: post
title:  "April 2017: State of the union of portable EEG"
---

There seems to be tons of interest in EEG right now. [Dabo-Med](https://www.dabo-med.com/the-modules-1/) sums it up quite well:

>   "EEG - reviving a classic"

And then there is the news that Elon Musk founded a company called NeuraLink that will work on connecting the 
human mind with AI. Their device might use some [EEG techniques](http://www.cityam.com/261954/heres-science-behind-neuralink-elon-musks-sci-fi-new) 
too. 

Here I capture some interesting recent developments in the world of portable EEG. 

# emotiv

[emotiv](https://www.emotiv.com/) has two portable EEG models. The first one has 10-15 sensors, and the promo video shows that it can be used
to track patient mental health, and to control drones / other connected devices. Their second model has fewer sensors and
looks less invasive. It was backed by a 
[Kickstarter campaign](https://www.kickstarter.com/projects/tanttle/emotiv-insight-optimize-your-brain-fitness-and-per) 
that raised $1.5 million. 

emotiv's summary:

>  Open your mind to -- Brainwear, Performance, Peace, Control

Holy crap! Control and Peace do not typically go together, do they? 

# Standards for EEG data

Authors of the paper, ["Preparing Laboratory and Real-World EEG Data for Large-Scale Analysis: A Containerized Approach"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4782059/), use a file based schema 
but introduce a standardized schema and metadata tagging format. 

They have also uploaded ~1 TB of EEG data. That's a nice start :)

- tag format: [http://www.hedtags.org/](http://www.hedtags.org/)
- data: [http://www.studycatalog.org/](http://www.studycatalog.org/)
- code: [https://github.com/VisLab](https://github.com/VisLab)

# Open source software for EEG

There are tons out there. Some interesting ones:
- Open-Source Brain-Computer Interface [https://github.com/OpenBCI](https://github.com/OpenBCI)
- NeuroScience with JavaScript [https://github.com/NeuroJS](https://github.com/NeuroJS)
  - Interesting dashboard by above folks [https://github.com/NeuroJS/openbci-dashboard](https://github.com/NeuroJS/openbci-dashboard)
