---
layout: post
title: "C++ Template Part 1"
categories: CPP
tags: [documentation,sample]
image:
  feature: 
  teaser:  
  credit: 
  creditlink: ""
---

<h2>Why do we need template?</h2> 
There will be many times when we are writing a program, we do not know the types that we need. 
There are mainly two ways to solve this program. Object oriented programming and generic programming. 
OOP deals with types that are not known until run time, while generic programming deals with type that are not known till compile time. 

When we program a generic program, we write code that is independent of any type. Template are the foundation of generic programming. 

<h2>Defining a template</h2?
{% highlight cpp linenos%}

template \<typename t\> bool bigger \<T\> (const T& V1, const T& V2 )
{
  if(V1 > V2)
  {
    return true;
  }
  else
  {
    return false;
  }
}
{% endhighlight %}
