---
layout: post
published: true
title: A typical data science workflow
---

I found the following very interesting quote describing a typical data-science application workflow:

> Data science applications revolve around the following paradigm:

```sh
Until (tired) {
  Data management
  Complex analytics
}
```

Note the usage of `tired` in the above construct. There is a lot of truth in this -- while working with data in either the data-management of analytics side, there is a lot of tedium that one must deal with. There are many obstacles in the path of getting insights from data e.g. data-format variabilities, software library inconsistencies, naming inconsistencies in the data etc. A lot of energy is spent in this phase -- naturally, there are significant economic implications for the "tired"-ness syndrome. 

One of the projects at our company where we are trying to alleviate the tired-ness of data-scientists is the [Insight](https://github.com/paradigm4/insight) project. Here, we harmonize data from hundreds of clinical trials (public and private) so that scientists can dive in directly into the analysis that they care about. Currently one of the top-five pharma companies in the world is using the API and UI-s of the Insight project.  

**PS**: The quote is from [an article](http://istc-bigdata.org/index.php/the-big-data-istc-a-retrospection-by-michael-stonebraker-samuel-madden-and-timothy-mattson/) by Michael Stonebraker, Samuel Madden and Timothy Mattson (with their experience in the world of data, they should know). The article covered the achievements of the ISTC big-data group at MIT in the last five years. Our company's database [SciDB](http://paradigm4.com) originated from this project, and is listed as one of the major achievements of the group. 