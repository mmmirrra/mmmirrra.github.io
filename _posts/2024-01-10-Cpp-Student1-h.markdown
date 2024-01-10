---
layout: post
title:  "C++: Student1.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Student1.h   
`Student1.h` : examples of base class and derived class - derived class - without virtual function // 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함   
   
```cpp
#pragma once
#include "Person1.h"

class Student1: public Person1 {				// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함
	string school;
public:
	void setSchool(const string& s) {
		school = s;
	}
	string getSchool() const {
		return school;
	}
	void print() const {
		Person1::print();
		cout << " goes to " << school;
	}
};
```
