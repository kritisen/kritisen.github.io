---
layout: post
title: SciDB; How to add an attribute column with a default missing reason
published: true
---

## SciDB: How to add an attribute column with a default missing reason

Here's the content of the original array:  
`iquery -aq "scan(A)" | head  
{Symbol_index,timestamp} a1,a2,a3  
{1,615} 1,null,null  
{1,1420} 1,null,null  
{1,17365} 1,null,null  
...  
`

I want to add a new null attribute to the end of the array.  
`iquery -aq "apply(A, b, double(null))" | head  
{Symbol_index,timestamp} a1,a2,a3,b  
{1,615} 1,null,null,null  
{1,1420} 1,null,null,null  
{1,17365} 1,null,null,null  
...  
`

But what if I want to distinguish from the nulls that are already present:  
`iquery -aq "apply(A, b, double(missing(1)))" | head  
UserException in file: src/array/MemChunk.cpp function: writeItem line: 923  
Error id: scidb::SCIDB_SE_EXECUTION::SCIDB_LE_ASSIGNING_NULL_TO_NON_NULLABLE  
Error description: Error during query execution. Assigning NULL to non-nullable attribute.  
`

The problem is that `missing(1)` is a null value, but the attribute it is being inserted into is a non-nullable attribute.

So the solution is to first add a nullable attribute, and then fill them with `missing(1)`'s. This would be a two step process. To do this in one query:  
`iquery -aq "apply(A, b, iif(true, double(missing(1)), double(null)))" | head  
{Symbol_index,timestamp} a1,a2,a3,b  
{1,615} 1,null,null,?1  
{1,1420} 1,null,null,?1  
{1,17365} 1,null,null,?1`
