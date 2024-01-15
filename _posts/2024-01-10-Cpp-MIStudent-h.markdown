---
layout: post
title:  "C++: MIStudent.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - MIStudent.h   
   
// 클래스 다중상속을 위한 클래스   
`MIStudent.h` : class for Multiple Inheritance   
   
```cpp
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Student4 {
	string school;
public:
	Student4(const string& s) : school(s) {}		// 생성자
	void printSchool() const {
		cout << "printSchool() school : " << school << endl;
	}
	void print() const {
		cout << "print() school : " << school << endl;
	}
};
```
