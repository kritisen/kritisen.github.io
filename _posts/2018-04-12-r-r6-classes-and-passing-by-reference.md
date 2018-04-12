---
layout: post
published: true
title: R R6 classes and passing by reference
subtitle: A simple test of passing by reference in R6 classes
---
By default, R6 classes are passed by reference. To avoid this, you need to use `clone(deep = TRUE)` while copying. 

Anyway what I wanted to capture here is that the pass by reference can be used smartly to change the value of a nested structure inside a function. 

Of course, this is a function side-effect that must be used with caution. As Hadley [puts it](https://adv-r.hadley.nz/r6.html), 

> modifying R6 inputs can lead to substantially simpler code in some cases.... Using R6 makes the code substantially simpler, at the cost of introducing subtle bugs. Fixing those bugs required careful placement of calls to $clone() to ensure that independent plots didn’t accidentally share scale data

My test code (and output) for demonstrating manipulating values inside a R6 class object is below:


```R
test1 = R6::R6Class(classname = 'test1',
            public = list(
              initialize = function(data) {
                private$.data = data
              },
              update_data = function(data) {
                private$.data = data
              },
              get_data = function() {
                private$.data
              }
            ),
            private = list(
              .data = NULL
            ) 
            )

test2 = R6::R6Class(classname = 'test2',
                    public = list(
                      initialize = function(value, x_test1) {
                        private$.value = value
                        private$.test1 = x_test1
                      },
                      update_test1 = function(data) {
                        private$.test1$update_data(data)
                      },
                      get_value = function() {
                        private$.value
                      },
                      get_test1_data = function() {
                        private$.test1$get_data()
                      }
                    ),
                    private = list(
                      .value = NULL,
                      .test1 = NULL
                    ) )


x1 = test1$new(data = 23)
x2 = test2$new(value = 11, x_test1 = x1)
x2$get_test1_data()
# 23 # <--- same value as x1 

x2$update_test1(data = 21)
x1$get_data()
# 21 # <--- you changed x2 but x1 got updated (x2 just stores a reference to x1)

x1$update_data(data = 33)
x2$get_test1_data()
# 33 # <--- you changed x1 but x2 got changed
````