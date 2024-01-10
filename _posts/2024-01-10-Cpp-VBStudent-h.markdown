---
layout: post
title:  "C++: VBStudent.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - VBStudent.h   
`VBStudent.h` : Student5 class inherits Person5 class as a virtual base class // Person5 클래스를 가상 기초 클래스로 상속받는 클래스 Student5   
   
```cpp
#pragma once
#include <iostream>
#include <string>
#include "VBPerson.h"
using namespace std;

class Student5 : virtual public Person5 {													// Person5를 가상 기초 클래스로 상속받는 클래스
	string school;
public:
	Student5(const string& n, const string& s) : Person5(n), school(s) {}
	void print() const {
		Person5::print();
		cout << "print() function in Student5 " << " goes to " << school << endl;
	}
};
```
