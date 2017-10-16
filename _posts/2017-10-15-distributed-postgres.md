---
layout: post
title: CitusData Distributed Postgres 
---

Another interesting DB -- distributed multi-node Postgres. Has CE (Github) and EE install options. And a SaaS option via AWS. 
http://www.dataengconf.com/the-challenges-of-distributing-postgres-a-citus-story

Some clippings:

https://github.com/citusdata/citus
> What is Citus?
>
> - Open-source PostgreSQL extension (not a fork)
> - Scalable across multiple machines through sharding and replication
> - Distributed engine for query parallelization
> - Database designed to scale multi-tenant applications
>
> Citus is a distributed database that scales across commodity servers using transparent sharding and replication. Citus extends the underlying database rather than forking it, giving developers and enterprises the power and familiarity of a relational database. As an extension, Citus supports new PostgreSQL releases, and allows you to benefit from new features while maintaining compatibility with existing PostgreSQL tools.

https://console.citusdata.com/users/sign_up?utm_source=citusdata.com&utm_medium=website&utm_campaign=downloadinstructions
> Citus Cloud helps when you have a need to scale your database beyond a single node, often beginning as early as 10 GBs of data—and allowing you to scale to 100s of Terabytes.


And the install doc works perfectly.
https://docs.citusdata.com/en/stable/installation/single_machine_deb.html#post-install
