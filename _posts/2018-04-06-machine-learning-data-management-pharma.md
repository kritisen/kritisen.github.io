---
layout: post
published: false
title: Machine learning for data management in pharma
subtitle: 'AI on the way in, AI on the way out'
---
[This article](https://www.forbes.com/sites/tomdavenport/2018/01/08/biting-the-data-management-bullet-at-glaxosmithkline/#f40637f5577e) is an excellent article about the data-management challenges faced by pharma companies. It outlines how GSK was faced with the self-realization that they are not equipped to make the best use of the vast quantities of digital data spewing out from their many clinical studies. 

They worked on three domains of data (with each domain, I am adding my estimate about the structure and size of the data):

1. Experimental data / "assays" (structured, large to very large)
2. Clinical trial data (unstructured, relatively small)
3. Genetic data (structured, very large depending on which level of information was captured)

# AI on the way in

They claim that the they ingested data at great speed to create one of the world's largest data-lakes. What made that possible? If I group the reasons cited by them into categories, they would fall under:

1. best design-practices ("standardized ontologies", "industry standard formats"), 
2. good software engineering ("integrated layer" to manage all domains)
3. big-data technology stack (HBase, Apache Hive, Hadoop)
4. AI ("The team would feed in the source trial data, and what the target format should look like—and then let the machine go to work")

Note that machine learning is being used to just ingest data into a central repository. ETL is one of the most time-consuming processes in data management (thank you "dirty data"), and algorithms are being used to speed this up (improving the ingest accuracy as the system gains experience). GSK collaborated with my company Paradigm4's CTO [Mike Stonebraker](https://en.wikipedia.org/wiki/Michael_Stonebraker)'s other company [TAMR](https://www.tamr.com/) to automate the data-ingest pipeilnes using a "probabilistic matching" approach. 

# AI on the way out

So the data is in? The next important challenge is cited by Chief Data Officer, [Mark Ramsey](https://www.linkedin.com/in/ramseymark). 

> ... the data foundation has been laid, but actually building the house—i.e., using the data for better science—will also require help from AI.

My ultimate summary:

> AI on the way in. AI on the way out. 
