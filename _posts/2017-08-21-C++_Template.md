---
layout: post
title: "C++ Template"
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
OOP deals with types that are not known until run time, while generic programming deals with the type that is not known until compile time. 

When we program a generic program, we write code that is independent of any type. Template is the foundation of generic programming. 

<h2>Defining a template</h2>
Here is how to define a simple template.
{% highlight cpp linenos%}
template <typename T> bool Bigger (const T& V1, const T& V2 )
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

When we are calling the function, the compiler will deduce the type of the parameter based on the type of parameter that is being passed in.
If the function is being called multiple times with different parameters each time, the compiler will create multiple instances of the function.
Note that a template function must have at least 1 parameter. 

<h2>NonType Template Parameters</h2>
We can also define template to take in nontype paramters. A non type represent a value rather than a type. 
A non type template are specified by a specific type name rather than typename or class.
These values are constant expressions, this allow the compiler to instantiate the template during compound time. 

{% highlight cpp linenos%}
template <unsigned N, unsigned M> 
int compare(const char (&P1)[N], const char (&P2)[M])
{
    return strcmp(P1,P2);
}


compare("hi", "mom");

{% endhighlight %}

<h2>Template Compilation</h2>
The compiler does not generate code when it sees the definition of a template. 
It will only generate code when it sees the instance of the template. 
For this very reason that the compiler only generates code when we instance it, this will affect how we organise our code. 

Normally when we call a function, the compiler only needs to know the declaration for the function. 
Similarly, when we use an object of a class, the compiler only needs to know the definition of the class and not the definition of the member function. 
For this reason, we will usually place function declaration and class definition in the header file and the definition of normal function and class member function in the source file.

However template are different. To instantiate a template function, the compiler needs to have the code that defines a function template or class template member function. 
As a result, headers for template usually include definition as well as declaration. 

<h2> Compilation Errors </h2>
There are three stages during which the compiler might flag an error. 

<h3>First stage </h3>
The first stage is when we compile the template. The compiler can detect syntax errors such as forgetting a bracket or a semicolon.

<h3>Second stage </h3>
The compiler will check for the number of the arguments is appropriate. Also it will check if a there the two arguments are of the same type. 

<h3>Third stage </h3>
The third stage happens when the template is being instantiate. It is only then the type related errors can be detected. Depending on how the compiler manages instantiation,
these errors maybe reported at linker stage. 