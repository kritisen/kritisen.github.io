---
layout: post
title: When "big-data" is big and when it is not
published: true
---

## When "big-data" is big and when it is not

A few months back, [my company's](http://paradigm4.com) Chief Data Scientist [Bryan Lewis](http://illposed.net/) gave a talk at the Boston R Users Group.

The theme of the talk was "thinking small about big data". The slides are available [here](http://illposed.net/boston_rug_sept_2015.html#1).

The following slide sort of reveals Bryan's sentiment quite well (hopefully lies within fair use limits):  

![enter image description here](https://github.com/ksens/ksens.github.io/blob/master/img/blewis-rug-boston-1.jpg?raw=true)

In his talk, Bryan goes on to show how seemingly "big" problems are easily tackled using a basic laptop computer (in fact, a really basic one). He notes two important ways of reducing "big"-data problems into more manageable sizes:

-   Projection
-   Changing bases

There are lots of links in the slides that give more detailed information about these methods.

There was something that is not covered in these slides:

> **-- when is "big"-data really BIG?**

Fortunately, in the Q&A session, someone asked the question and Bryan gave an explanation along the following lines:

Basically, whenever we are closer to the data-source, that is where the data is really big. For example, Bryan's talk shows that certain problems involving genetics (more specifically, variant data) can be solved without "big"-data infrastructure. However the precursor to variant data are:

-   Raw data (in order of Petabytes)
-   Aligned sequences (in order of Terabytes)

While handling those datasets, it is imperative to use big-data solutions. The analogy works in many other fields and we can think of some other examples of "close-to-source" data -- the raw trades and quotes data used for quantitative finance applications, a barrage of signals from sensors in Internet-of-Things applications.

Ultimately, the main summary is this:

**Think before jumping into the "big"-data bandwagon. Remember, some big is really small, and then there is the really BIG big.**
