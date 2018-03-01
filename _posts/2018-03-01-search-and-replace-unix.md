---
layout: post
title: Recursive Search and Replace in Unix
published: true
---

Mainly archiving this for the benefit of future-me. 

## The problem

Given an a list of files where I want to search and replace all whole-word occurences of `reference_name` with `chromosome`

```sh
grep -rw reference_name * | head
load/formats.yaml:        chrom:   reference_name
load/load-functions.R:    df1$reference_name = gsub('chr', '', df1$reference_name)
load/load-helper.R:    new_features$reference_name = 'unknown'
load/load-helper.R:    new_features$reference_name = 'unknown'
# .. hundreds of other occurences
```

## The solution

```sh
string_to_search=reference_name
string_to_replace=chromosome
sed -i 's/\<$string_to_search\>/$chromosome/g' `grep -rw -l $string_to_search *`
```

where
- `-l` is for giving location of file only (not the entire output) [[Link](https://stackoverflow.com/questions/6637882/how-can-i-use-grep-to-show-just-filenames-no-in-line-matches-on-linux)]
- `-w` is for whole word occurences only
- `\<$string_to_search\>` is the whole word occurence search equivalent in `vim`
