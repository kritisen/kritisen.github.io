---
layout: post
title: Thesis flyer
published: true
---

## Thesis flyer

**What is CT?**

CT stands for computed tomography. A clinical CT scanner is shown in Fig. A. Figure B shows the working principle, by which x-ray beams pass through the body to be detected as projections. A set of projections across various angles forms a tomography (or a sinogram). Figure C shows a very simplistic image reconstruction problem where the measured projection data: {7,2,5,4}, and the unknowns { x1, x2, x3, x4} obey the following:

                                            x1 + x2 = 5,

                                      x1 + x3 = 7, … and so on.

This reconstruction problem can be resolved by simply solving a set of simultaneous equations. Unfortunately, the most common scenarios involve 106 unknowns and a greater number of measurements! More complicated reconstruction algorithms have to be used (the most common being filtered back projection or FBP).

![enter image description here](https://github.com/ksens/ksens.github.io/blob/master/img/reconExpln1-1024x624.jpg?raw=true)

**What is micro-CT?**

Clinical CT has a resolution of ~1 mm. Micro-CT has a resolution of ~1 µm (i.e. a magnification factor of 1000).

**What limits the imaging capability of micro-CT?**

Scan time is extremely long (may be > 6 hours per scan). Also a mathematical property demands that, for exact reconstruction, the x-ray beam must cover the entire sample. This restriction severely limits the allowable sample size?

**What is compressed sensing (CS)?**

CS is a new mathematical theory that allows significant improvements in CT reconstruction by the use of certain iterative reconstruction algorithms like SART-TV (simultaneous algebraic reconstruction technique, with total variation minimization).

**What is the contribution of this thesis?**

This thesis aims to show that:

_compressed sensing (CS) based reconstruction methods can enhance the imaging capability of micro-CT scanners._
