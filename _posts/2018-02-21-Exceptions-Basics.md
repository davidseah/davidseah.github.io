---
layout: post
title: "Exceptions Basics"
categories: CPP
tags: [CPP]
image:
  feature: 
  teaser: 
  credit: 
  creditlink: ""
---

I will be starting my blog from this video lessons I am currently taking from Learn Advanced C++ Programming by 
John Purcell. I will be documenting what I learn from the videos. 
This will help me to remember what I learned and also a reference in future. 


So imagine we have a function MightGoWrong() that might potential causes some issues that your program cannot recover from. 
For example unable to allocate a huge chunk of memory. 

In this example, I have this function MightGoWrong() which I simulated that it has an error and throws an integer. 
To catch the exception, we can use the <b>try</b> and <b>catch</b> keyword. 
Once we catch the error we can do a simple printing of the error and the program will continue to run.

{% highlight cpp linenos%}

#include <iostream>
using namespace std;

void MightGoWrong()
{
  bool error = true;
  if(error)
  {
    throw 8;
  }
}

int main()
{
  try
  {
    MightGoWrong();
  }
  catch(int e)
  {
    cout >> "error" >> endl;
  }

  return 0;
}

{% endhighlight %}