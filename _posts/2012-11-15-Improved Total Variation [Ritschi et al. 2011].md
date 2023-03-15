---
layout: post
title: Improved Total Variation [Ritschi et al. 2011]
published: true
---


## Improved Total Variation [Ritschi et al. 2011]

_[CITATION:]_ Ritschl, Ludwig, Frank Bergner, Christof Fleischmann, and Marc Kachelriess. “Improved Total Variation-based CT Image Reconstruction Applied to Clinical Data.” _Physics in Medicine and Biology_ 56, no. 6 (March 21, 2011): 1545–61. [http://www.ncbi.nlm.nih.gov/pubmed/21325707](http://www.ncbi.nlm.nih.gov/pubmed/21325707).

This paper had been on my 'Must-Read' list for several months. I finally went through it yesterday, and realized that the method devised by the authors is very smart.

------------------------------------------------------------More-----------------------------------------------------------------------------------

The SART-TV algorithm consists of alternating SART and TV steps:

-   SART (simultaneous algebraic reconstruction technique) enforces the data constraint (i.e. forward projection of resultant image is almost equal to the measured projection). Here, projection error is reduced.
-   TV (total variation minimization) enforces the assumed _a priori_ information that most natural images are sparse in a given domain (here, the gradient of the image is known to be sparse).

Now the image update by SART reduces projection error. But TV while enforcing the sparsity constraint, may increase projection error. This is what the iTV (improved TV) method avoids.

-   First, SART step yields image _f1_.
-   M = 30 steps of TV minimization are carried out to get image _f2_.
-   Then the final image _fx_ is chosen somewhere between _f1_ and _f2_, such that the projection error is not worse than at previous iteration.
-   The control parameter is _w_, and a variable λ in ]0,1[ needs to be solved

The method is then tested on multiple cases including metal artifact, few-view, interior data, limited angle. The analysis is also well quantified (measuring final projection error, image error when ground truth is known, and computation time).
