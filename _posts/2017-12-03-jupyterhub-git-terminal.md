---
layout: post
title: Liking JupyterHub but missing git 
---

Firstly I am a bit torn about Jupyter / JupyterHub. On one side, jupyter notebooks are great for 
turning out beautiful tutorials and across two of our (Paradigm4's) key languages e.g. I used it for creating R tutorials 
during the [HMS hackathon](https://hms-dbmi.github.io/hackathon-Sept2017); other folks at our company have made great python 
tutorials for customers. 

However I am currently trying to to use it for collaboration with another data-scientist, and I find the code sharing mechanism 
not so useful. Mainly, I miss the fact that jupyter notebooks have no meaningful diff feature. 
Git version tracking is almost useless (versions can be maintained -- but without the diff, 
it is near impossible to track changes). 
Other companies ([link](https://kyso.io/)) seem to be thinking about the version tracking issue. 

Today I found that jupyterhub does [allow terminal access](https://stackoverflow.com/questions/34941546/is-there-a-way-to-integrate-git-with-jupyter-and-have-a-version-control-over-the) (which is a great relief):

Either way, these notebooks appear to be a standard thing these days. Many folks are getting into the business of 
creating notebooks that embed code and results
- [Azure](https://notebooks.azure.com/)
- [Google](https://cloud.google.com/datalab/)
- [Spark notebooks](https://zeppelin.apache.org/) (a data-scientist at amazon says this is the new thing there -- mainly because of the native spark connection)
...

Speaking of competition in this space, there was recently some interesting twitter chatter 
comparing different options on a thread started by Jake Van der Plas (our scidbpy 1.0 creator) 
https://twitter.com/jakevdp/status/923936168521097216. Azure is criticized. Many other players are mentioned. 

Interesting space to watch out for. 
