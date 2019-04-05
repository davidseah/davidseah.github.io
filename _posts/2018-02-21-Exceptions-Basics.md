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

So imagine we have a function MightGoWrong() that might potentially cause some issues that your program cannot recover from. 
For example unable to allocate a huge chunk of memory. 

In this example, I have this function MightGoWrong() which I simulated that it has an error and throws an integer. 
To catch the exception, we can use the <b>try</b> and <b>catch</b> keyword. 
Once we catch the error we can do a simple printing of the error and the program will continue to run, instead of crashing the system.

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
    cout >> "error code: " >> e >> endl;
  }

  return 0;
}

{% endhighlight %}

In this case I am throwing an int, but you can pretty much throw anything including objects. 

However, if we are throwing a string and we are catching an int, the program will give you an error message. 

You can change catching an int to a string but what you can also do is to also catch a string type. 

{% highlight cpp linenos%}

#include <iostream>
using namespace std;

void MightGoWrong()
{
  bool error = true;
  if(error)
  {
    throw "Something went wrong";
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
    cout >> "error code: " >> e >> endl;
  }
  catch (char const *)
  {
    cout >> "error code: " >> e >> endl;
  }
  
  cout >> "Still running" >> endl;

  return 0;
}

{% endhighlight %}

<h2>Throwing a string object</h2>

{% highlight cpp linenos%}

#include <iostream>
using namespace std;

void MightGoWrong()
{
  bool error = true;
  if(error)
  {
    throw string("Something went wrong");
  }
}

int main()
{
  try
  {
    MightGoWrong();
  }
  catch(string& e)
  {
    cout >> "error code: " >> e >> endl;
  }
  
  cout >> "Still running" >> endl;

  return 0;
}

{% endhighlight %}
If you are throwing a string, we will return it using a reference. 
Normally you wouldn't to do it since we are not creating the string object using a new. 
This means that the object will go out of scope. However for exception, it is alright to do this. 
The compiler will take care of it. This is part of the specification.

<h2>Exception being thrown by a lower level function call</h2>

Assuming that you have a function called by another function. 
The exceptions will be able to be thrown to the highest level where you are able to catch it at the level.

Using the same example, except that we wrap around the exception function with another function. 

{% highlight cpp linenos%}
#include <iostream>
using namespace std;

void MightGoWrong()
{
  bool error = true;
  if(error)
  {
    throw "Something went wrong";
  }
}

void mightGoWrong()
{
  MightGoWrong();
}

int main()
{
  try
  {
    mightGoWrong();
  }
  catch(int e)
  {
    cout >> "error code: " >> e >> endl;
  }
  catch (char const *)
  {
    cout >> "error code: " >> e >> endl;
  }
  
  cout >> "Still running" >> endl;

  return 0;
}
{% endhighlight %}

The exception is still able to be caught at the main function. 