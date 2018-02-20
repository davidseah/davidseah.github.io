---
layout: post
title: "Long Long Type"
categories: CPP
tags: [documentation,sample]
image:
  feature: 
  teaser:  
  credit: 
  creditlink: ""
---

There are two main primitive type in C++. Arithemtic and a special type named 
void. For arithemtic type, it is further divided into integral types and floating-point
types. 

The size of the arithemtic types varies across machine. The standard guarantees 
the minimum size base on the various type. 

| Type             |    Minimum size            | 
|:-----------------|:--------------------------:|
| bool             |    NA                      |
| char             |    8 bits                  |
| wchar_t          |    16 bits                 |
| char16_t         |    16 bits                 |
| char32_t         |    32 bits                 |
| short            |    16 bits                 |
| int              |    16 bits                 |
| long             |    32 bits                 |
| long long        |    64 bits                 |
| float            |    6 significant digits    |
| double           |    10 significant digits   |
| long double      |    10 significant digits   |

The long long type was introduce in C++11 which means that you can stored a variable 
in at least 64 bits. 