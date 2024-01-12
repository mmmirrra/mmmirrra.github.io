---
layout: post
title:  "C++: NameObj.cpp : etc sourceFile"
date:   2024-01-09 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - etc sourceFile - NamedObj.cpp   
// 생성자, 소멸자 동작 예제   
`NamedObj.cpp` : example of how constructor and destructor work   
   
```cpp
#include <cstring>
#include "NamedObj.h"

NamedObj::NamedObj(const char* s)		// 생성자
{
	name = new char[strlen(s) + 1];
	strcpy(name, s);
	id = ++nConstr;
}

NamedObj::~NamedObj()				// 소멸자
{
	++nDestr;
	delete[] name;
}

int NamedObj::nConstr = 0;
int NamedObj::nDestr = 0;
```
