---
layout: post
title:  "Google search for genomic data"
---
# Google search for genomic data

GA4GH (Global Alliance for Genomics and Health) http://genomicsandhealth.org/ talks about building 
the "Google search for genomic data" using RESTful API. 

I found an interesting example here:
"A global search engine for genetic mutations." https://beacon-network.org

The example search suggested on the site is: `13 : 32936732 G > C`

I tried another random one from SNPedia: `1 : 155204793 C > T`

Notice how the link is formatted:
https://beacon-network.org/#/search?chrom=1&pos=155204793&ref=C&allele=T&rs=GRCh37

I imagine that the search URL structure is then passed verbatim to other databases that are registered on the Beacon network. 

Pretty interesting!
