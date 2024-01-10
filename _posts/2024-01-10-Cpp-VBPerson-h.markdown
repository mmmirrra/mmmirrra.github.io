---
layout: post
title:  "C++: VBPerson.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - VBPerson.h   
`VBPerson.h` : virtual base class - Person5 class // 가상 기초 클래스 - Person5 클래스   
   
```cpp
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Person5 {		// 가상 기초 클래스
	string name;
public:
	Person5(const string& n) : name(n) {}
	virtual ~Person5() {}		// 가상함수 소멸자
	virtual void print() const {		// 가상함수
		cout << "print() function in Person5 : " << name;
	}
};
```
