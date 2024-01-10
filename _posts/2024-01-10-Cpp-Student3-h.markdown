---
layout: post
title:  "C++: Student3.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Student3.h   
`Student3.h` : examples of base class and derived class - derived class - include virtual function // 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 포함   
   
{% highlight cpp %}
#pragma once
#include <iostream>
#include <string>
#include "Person3.h"
using namespace std;

class Student3 : public Person3 {												// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 포함
	string school;
public:
	Student3(const string& n, const string& s) : Person3(n), school(s) {

	}
	string getSchool() const {
		return school;
	}
	void print() const {
		Person3::print();
		cout << " goes to " << school;
	}
	void printVirtual() const override final {									// 기초 클래스의 printVirtual() 함수가 가상함수이므로 파생 클래스의 함수도 가상함수가 됨. 기초 클래스의 가상함수를 재정의했다는 것을 알리기 위해 override 키워드 사용. 가상함수를 다음 파생 클래스에서 더이상 재정의하지 못하게 하기 위해 final 키워드 사용
		Person3::printVirtual();
		cout << " goes to " << school;
	}
};
{% endhighlight %}
