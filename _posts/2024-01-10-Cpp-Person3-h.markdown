---
layout: post
title:  "C++: Person3.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Person3.h   
`Person3.h` : examples of base class and derived class - base class - include virtual function // 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 포함   
   
{% highlight cpp %}
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Person3 {									// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 포함 
	string name;
public:
	Person3(const string& n) : name(n) {

	}
	string getName() const {
		return name;
	}
	void print() const {
		cout << name;
	}
	virtual void printVirtual() const {			// 기초 클래스의 함수를 가상함수로 만듦
		cout << name;
	}
};
{% endhighlight %}
