---
layout: post
published: true
title: Caching over and above the primary storage
subtitle: The omnipresence of caching
---
People do all sorts of optimizations over their primary storage layer. AWS has built a whole product around this kind of caching mechanism (to get sub-millisecond response times) https://aws.amazon.com/elasticache/redis/

Their diagram below really outlines the prevalent architecture very well:

! [elasticache](https://github.com/ksens/ksens.github.io/raw/master/img/elasticache_diagram_Caching.png)

- Client layer with UI's, apps etc.
- Storage layer with multiple databases / file-systems
- Caching layer in between

Writing and managing a caching layer is not easy. Reminds me of the famous CS phrase:

> There are only two hard things in Computer Science: cache invalidation and naming things.
> 
> -- Phil Karlton