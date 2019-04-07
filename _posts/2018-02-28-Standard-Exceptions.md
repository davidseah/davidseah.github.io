---
title: "Standard Exceptions"
categories:
  - CPP
tags:
# last_modified_at: 2017-03-09T14:25:52-05:00
---
Catching an exception from a constructor

You are able to catch an exceptions being thrown from a constructor.  Let say we are allocating a huge amount of memory in the constructor. An exception will be thrown by C++. 
However, since an exception is being thrown, the constructor will not be able to complete properly and the program will be terminated. 

But if we catch the exceptions properly, we are able continue the program elegantly with a print out of what went wrong. 

C++ throws bad_alloc when it is unable to do a memory allocation, bad_alloc is a child class of exception which includes a <i>.what() </i> which tells us the error messages.

Also remember to use reference for object in exceptions. 

```cpp
#include <iostream>
using namespace std;

class CanGoWrong
{
  public:
  CanGoWrong()
  {
    char * Memory = new char[99999999999];
    delete []Memory;
  }
};

int main()
{
  try{
  
    CanGoWrong wrong;
  }
  catch(bad_allow & e)
  {
    cout << "error: " << e.what() << endl;
  }
  
  return 0;
}
```