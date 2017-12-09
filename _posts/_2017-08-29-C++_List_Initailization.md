---
layout: post
title: "List Initialization
categories: CPP
tags: [documentation,sample]
image:
  feature: 
  teaser:  
  credit: 
  creditlink: ""
---

There are a couple of ways to  initialise a varaible in C++. From C++11 onwards, they have added a new way of initializing, which is the list initialization. 
List initialization is representation by a curly brace. 

There is one important property of list initailization, which is the compiler is not able to initalize anything that will lead to the lost of data.

{% highlight cpp linenos%}
long double pi = 3.1415926536;
int a{pi}, b = {pi}; //this will not be able to compiler
int c(pi), d = pi; //this is okay.
{% endhighlight %}

The compiler will reject the use of a and b, as using a long double to initalize a int will lighly lead to a loss of data.
Also int will be too small to hold long double. 


