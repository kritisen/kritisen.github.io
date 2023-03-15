---
layout: post
title: Optimizing bin width for K-Edge Imaging [He et al., 2012]
published: true
---

## Optimizing bin width for K-Edge Imaging [He et al., 2012]

_[Citation:]_ He, Peng, Biao Wei, Wenxiang Cong, and Ge Wang. “Optimization of K-edge Imaging with Spectral CT.” _Medical Physics_ 39, no. 11 (2012): 6572. [http://link.aip.org/link/MPHYA6/v39/i11/p6572/s1&Agg=doi](http://link.aip.org/link/MPHYA6/v39/i11/p6572/s1&Agg=doi)

Peng He was a visiting scholar at my lab. While I was familiar with his work on the MARS-CT scanner, I did not know the details of the work he did on optimizing K-edge imaging. So I undertook a detailed study of this paper, which describes his work on this topic.

      -------------------------------------------------------More---------------------------------------------------------------------

In spectral CT, projection images are acquired at different energies. The main motivation is to harness the K-edge property of materials, by which:

Attenuation coefficient µ decreases with increasing X-ray energy. At the K-edge, there is a sudden increase in µ, and then µ begins to drop again.

Thus if we take one image below the K-edge, and another image above the K-edge, there should be a distinct contrast between the two images. And thus allowing elemental characterization (two materials may have same µ, but will have different K-edge).

Now there is also a width of the energy bin which needs to be selected. This paper optimizes the energy bin width in such a fashion that the distinction between the two images is maximized.

The distinction between images is measured in terms of SDNR (signal difference to noise ratio) which is equivalent to CNR (contrast to noise ratio). The paper derives expressions for SDNR based on the following:

-   x-ray source (mean photon count **_I0_**) assumed to be characterized by Poisson distribution
-   **_g_**: attenuation coefficients of contrast medium and other material in imaged object
-   **_C(E)_**: energy distribution function of x-ray source. Number of photons in each energy window is assumed to be constant

The expression for SDNR is first used to determine the domain (i.e min, max) of the bin-width search. Then within the search domain (**_0, w__max**), the bin-width **_w__opt** that yields the highest SDNR is determined.

Some key observations that are used:

-   Average µ on left side of K-edge < Average µ on right side i.e. µL < µR
-   Minimum bin-width = 0
-   Maximum bin-width corresponds to µL = µR
