---
layout: post
title:  "C++: VBParttime.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - VBParttime.h   
`VBParttime.h` : class that inherit Student5 class and Employee2 class - Parttime2 class // Student5와 Employee2를 상속받는 클래스 - Parttime2 클래스   
   
```cpp
#pragma once
#include "VBStudent.h"
#include "VBEmployee.h"

using namespace std;
class Parttime2 : public Student5, public Employee2 {	// Student5와 Employee2를 상속받는 클래스. Person5는 가상 기초 클래스로 상속 받았으므로 이 Parttime2 객체 내에 Person5는 1개만 상속되어 존재함
public:
	Parttime2(const string& n, const string& s, const string& c) : Person5(n), Student5(n, s), Employee2(n, c) {}	// 다중상속을 받았을 때는 Person5의 생성자를 명시적으로 호출하여 가상 기초 클래스를 초기화 해야 함
	void print() const {
		cout << "print() function in Parttime2 : " << endl;
		Student5::print();
		Employee2::print();
	}
};
```
