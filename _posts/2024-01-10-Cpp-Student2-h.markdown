---
layout: post
title:  "C++: Student2.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Student2.h   
   
// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함 - Person2 생성자를 통해 데이터멤버 초기화   
`Student2.h` : examples of base class and derived class - derived class - without virtual function - initialize data members through the constructor of Person2   
   
```cpp
#pragma once
#include "Person2.h"

class Student2 : public Person2 {	// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함
	string school;
public:
	Student2(const string& n, const string& s) : Person2(n) {	// Person2 생성자를 통해 name 데이터멤버를 초기화 함
		cout << "constructor of Student2" << endl;
		school = s;
	}
	~Student2() {
		cout << "destructor of Student2" << endl;
	}
	void setSchool(const string& s) {
		school = s;
	}
	string getSchool() const {
		return school;
	}
	void print() const {
		Person2::print();
		cout << " goes to " << school;
	}
};
```
