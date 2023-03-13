---
layout: post
title: DIY DB Do-It-Yourself DB
published: true
---

## DIY DB: Do-It-Yourself DB

DIY DB (do-it-yourself database) seems to be a recurrent theme in the database industry.

Just yesterday, LinkedIn [announced](https://engineering.linkedin.com/blog/2015/10/open-sourcing-paldb--a-lightweight-companion-for-storing-side-da) PalDB:

> When this side data becomes large it can be a bottleneck for the applications that depend on them.
> 
> To solve this problem we created PalDB ...

And at [this wonderful article](http://www.wired.com/2015/10/meet-walking-dead-hp-cisco-dell-emc-ibm-oracle) describing how Amazon, Google, Facebook etc. decided to forego the then-traditional route of buying database and other hardware services from the giants of that era:

> They (i.e. Amazon, Google and Facebook) couldn’t use databases from Oracle. It was too expensive. And it couldn’t scale. ... They built their own servers, their own storage gear, their own networking gear, their own **databases** and other software for juggling information across all this hardware.

[This whitepaper](https://pages.questexweb.com/Evolving-Data-Architecture.html?source=spon) from FierceBigData (requires signup for download) mentions something similar too:

> In the course of just a few years, the rapid rise of NoSQL databases from niche offerings to increasingly mainstream data storage vehicles has shown just how strong the need has grown for systems that offer an alternative to the rigidity of SQL database architectures.

My company Paradigm4 also works on a similar _mantra_. We designed SciDB as [a super-efficient store for multidimensional arrays](http://www.paradigm4.com/) (that includes data from genomics, medical imaging, quantitative finance and many other fields).

Ultimately, this seems to be an important theme in the database industry:

> **If you do not like the current technology, and you think you can do better, build it yourself.**
