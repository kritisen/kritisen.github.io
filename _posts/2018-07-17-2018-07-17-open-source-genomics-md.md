---
layout: post
published: false
title: 2018-07-17-open-source-genomics.md
---
## Open source genomics tools 

I was interested in knowing more about available open-source genomics tools e.g. GATK, Hail, GenomicsDB/TileDB, ADAM. Capturing some notes from my web-search below. 

### Summary

#### TCGA

1. [TCGA-assembler](http://www.compgenome.org/TCGA-Assembler/) is a set of user friendly R functions to download data from TCGA firehose at Broad. 
2. The XenaBrowser allows beautful visualizations across multiple genomic and phenotypic data types
![xenabrowser snapshot](https://pancanatlas.xenahubs.net/download/meta/screenshot.png). [[1](https://xenabrowser.net/datapages/?host=https%3A%2F%2Fpancanatlas.xenahubs.net)]. Their paper is quite popular with [158 citations since 2014](https://scholar.google.com/scholar?cites=7434599276556022939&as_sdt=40000005&sciodt=0,22&hl=en&authuser=1). 

#### Generic tools

1. ADAM is the successor to PLINK/SEQ
2. GenomicsDB/TileDB is not currently integrated with Hail (but that might change). Both tools are from the Broad Institute. 
3. 
10. PCA capability exists in multiple software -- (a) PLINK/SEQ, (b) Hail

### Details to support summary

#### TCGA

1. 

#### Generic tools

10(a). 
Rivas, Manuel A., et al. "Insights into the genetic epidemiology of Crohn's and rare diseases in the Ashkenazi Jewish population." PLoS genetics 14.5 (2018). [Link](http://journals.plos.org/plosgenetics/article?id=10.1371/journal.pgen.1007329)

Principal Component Analysis (PCA) was done in each ancestry group using the 21,066 variants. Sample QC was done using the Hail software while PCA, differential missingness and sample relatedness analysis was done using PLINK. Hail is an open-source software framework for scalably and flexibly analyzing large-scale genetic data sets (https://github.com/broadinstitute/hail). Allele balance was calculated using PLINK/SEQ (https://atgu.mgh.harvard.edu/plinkseq/)

10(b).

