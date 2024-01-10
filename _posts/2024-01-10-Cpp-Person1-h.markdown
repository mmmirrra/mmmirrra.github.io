---
layout: post
title:  "C++: Person1.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Person1.h   
`Person1.h` : examples of base class and derived class - base class - without virtual function // 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 미포함   
   
```cpp
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Person1 {									// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 미포함
	string name;
public:
	void setName(const string& n) {
		name = n;
	}
	string getName() const {
		return name;
	}
	void print() const {
		cout << name;
	}
};
```
