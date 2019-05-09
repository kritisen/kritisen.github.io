---
layout: post
published: true
title: Find largest objects in R
---

Find largest objects in R

```R
sort(
    sapply(ls(), 
    function(objname) {
        as.numeric(
            gsub(" Mb", "", 
                format(
                  object.size(
                    get(objname)
                    ), 
                    units = "MB")))), 
    decreasing = T)
```

Results in 

```
                                     submatrix                                             L1 
                                        6806.8                                          126.3 
                                     sample_df                              sample_df_in_hdf2 
                                         126.1                                          112.8 
...
                                   project_id2                                         rangei 
                                           0.0                                            0.0 
                               uniq_identifier 
                                           0.0 
```
