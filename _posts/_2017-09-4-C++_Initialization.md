---
layout: post
title: "C++ Class Template"
categories: CPP
tags: [documentation,sample]
image:
  feature: 
  teaser:  
  credit: 
  creditlink: ""
---
A class template is different from a function template in that a compiler cannot deduce the type in the parameter.
Instead we have to supply the compiler andditional information by use the angle bracket after the template's name. 
The additional information is to be use in place of the template parameter.

Like the template function, a class template begin with the keyword temple. 

{% highlight cpp linenos%}

template <typename T> class Blob
{
  public:
    typedef T value_type;
    typedef typename std::vector<T>::size_type size_type;
    
    //constructor
    Blob();
    Blob(std::initializer_list<T> il);
  
  
  
  
  private:
  
  
}



{% endhighlight %}
