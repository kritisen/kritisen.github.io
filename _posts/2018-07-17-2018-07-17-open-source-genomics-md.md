---
layout: post
published: false
title: 2018-07-17-open-source-genomics.md
---
# Software tools for genomics tertiary analysis

I work for Paradigm4, the creators of SciDB. The views expressed in this blog are my own.

At Paradigm4 / SciDB, we do a lot of work on genomics data e.g.
- [Global biobank engine for UK Biobank data and other biobanks](https://biobankengine.stanford.edu/), 
- [Paper by Manuel Rivas' group](https://www.biorxiv.org/content/biorxiv/early/2018/03/19/257162.full.pdf), 
- [REVEAL-Genomics API](https://paradigm4.github.io/reveal-genomics-docs/)
- [PCA in SciDB](https://twitter.com/andyhpalmer/status/541955430118080512), 
- [SciDB SPARK comparison](https://link.springer.com/chapter/10.1007/978-3-319-60131-1_34), 

This post is my brief **subjective** review of other genomics solutions.

Mainly, I was interested in knowing more about

- available open-source genomics tools for tertiary analysis in genomics (see image below). Capturing some notes from my web-search below
- specialized resources for TCGA

## Tertiary analysis tools out there

This [Cloudera blog post](http://blog.cloudera.com/blog/2016/04/genome-analysis-toolkit-now-using-apache-spark-for-data-processing/) provides a good explanation of tertiary analysis
![three-levels-of-analysis](http://blog.cloudera.com/wp-content/uploads/2017/04/Pipeline.png)

GATK and similar tools (?) are used for primary and secondary analysis, while (according to [this Reddit post](https://www.reddit.com/r/bioinformatics/comments/5t7idb/large_scalable_variant_stores/)) the following tools are used for tertiary analysis  

- Hail (Broad Institute) (successor to PLINK / SEQ)
- GenomicsDB / TileDB (Broad Institute and Intel)
- ADAM (U.C. Berkeley)
- SciDB (Paradigm4)
- GQT (U. Utah)

### Some observations about these tools

2. Hail (from Broad Instute) is the successor to PLINK (Harvard) [[Link](https://blog.cloudera.com/blog/2017/05/hail-scalable-genomics-analysis-with-spark/)], the last version of which was released in 2014 [[Link](http://zzz.bwh.harvard.edu/plink/)]
3. As of March 2018, GenomicsDB/TileDB was not integrated with Hail [[Link](http://discuss.hail.is/t/genomicsdb-integration/434)]. But that might change; both tools are from the Broad Institute. 
4. Found references to PCA on genomic data in multiple cases -- 
    + Paper that used PLINK/SEQ for PCA [[Link](http://journals.plos.org/plosgenetics/article?id=10.1371/journal.pgen.1007329)]. Also see footnote 1. 
    + [Blog post from Cloudera](http://blog.cloudera.com/blog/2016/04/genome-analysis-toolkit-now-using-apache-spark-for-data-processing/) that used Hail on Spark. 
5. Found links on Hail integration with [Databricks](https://www.slideshare.net/SparkSummit/hail-scaling-genetic-data-analysis-with-apache-spark-keynote-by-cotton-seed), [Cloudera](https://blog.cloudera.com/blog/2017/05/hail-scalable-genomics-analysis-with-spark/)

## TCGA tools

1. [TCGA-assembler](http://www.compgenome.org/TCGA-Assembler/) is a set of user friendly R functions to download data from TCGA firehose at Broad. Their paper is quite popular with [158 citations since 2014](https://scholar.google.com/scholar?cites=7434599276556022939&as_sdt=40000005&sciodt=0,22&hl=en&authuser=1). 
2. The XenaBrowser allows beautful visualizations across multiple genomic and phenotypic data types. [[Link](https://xenabrowser.net/datapages/?host=https%3A%2F%2Fpancanatlas.xenahubs.net)]. 
![xenabrowser snapshot](https://pancanatlas.xenahubs.net/download/meta/screenshot.png). 

## Aside

A [beautiful cartoon explanation of GWAS](https://www.broadinstitute.org/visuals/explainer-genome-wide-association-studies) from the Broad, using more images like the one below:
![cartoon-GWAS](https://www.broadinstitute.org/files/landing_items/Explainer-close-up.jpg)

## Footnotes

1. From Rivas, Manuel A., et al. "Insights into the genetic epidemiology of Crohn's and rare diseases in the Ashkenazi Jewish population." *PLoS genetics* 14.5 (2018)

"Principal Component Analysis (PCA) was done in each ancestry group using the 21,066 variants. Sample QC was done using the Hail software while PCA, differential missingness and sample relatedness analysis was done using PLINK. Hail is an open-source software framework for scalably and flexibly analyzing large-scale genetic data sets (https://github.com/broadinstitute/hail). Allele balance was calculated using PLINK/SEQ (https://atgu.mgh.harvard.edu/plinkseq/)"


## NOTE

If images used here violate copyright terms, please [let me know](http://kritisen.com/aboutme/). 
