---
title: "Custom Exceptions"
categories:
  - CPP
tags:
# last_modified_at: 2017-03-09T14:25:52-05:00
---
You can create your own exceptions. It is a good idea to derive it from the standrd exception. 

Let's create an exception. The name of the exception should give you an idea what the exception is about. 
Since this is an example, I will give it a generic name. In standard exception, it contains a virtual function called what(). 
We are going to override it. Notice that it has a const throw() keyword in the function. This means that the function cannot throw an exception.
This check is at runtime and not compile time. So it is not a good idea to use it. 

Next, I am going to create a class Test which throws myException during construction. 

In my main, I create a Test Object, which I will try to catch the error. Of course, we have to catch the error with the type myException. 
```cpp
#include <iostream>
#include <exception>

using namespace std;

class myException: public exception
{
  public:
  virtual const char* what() const throw(){
    return "Something bad happen here";
  }
};

class Test
{
  public:
  Test()
  {
    throw myException();
  }
};

int main()
{
  try
  {
  Test test;
  }
  catch(myException & e)
  {
    cout  << "error " << e.what() << endl;
  }

  return 0;
}
```