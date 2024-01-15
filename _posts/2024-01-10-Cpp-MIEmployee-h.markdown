---
layout: post
title:  "C++: MIEmployee.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - MIEmployee.h   
   
// 클래스 다중상속을 위한 클래스   
`MIEmployee.h` : class for Multiple Inheritance   
   
```cpp
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Employee1 {
	string company;
public:
	Employee1(const string& c) : company(c) {}		// 생성자
	void printCompany() const {
		cout << "printCompany() company : " << company << endl;
	}
	void print() const {
		cout << "print() company : " << company << endl;
	}
};
```
