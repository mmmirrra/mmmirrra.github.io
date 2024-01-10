---
layout: post
title:  "C++: VBEmployee.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - VBEmployee.h   
`VBEmployee.h` : Employee2 class inherits Person5 class as a virtual base class // Person5 클래스를 가상 기초 클래스로 상속받는 클래스 Employee2   
   
{% highlight cpp %}
#pragma once
#include <iostream>
#include <string>
#include "VBPerson.h"
using namespace std;

class Employee2 : virtual public Person5 {														// Person5를 가상 기초 클래스로 상속받는 클래스
	string company;
public :
	Employee2(const string& n, const string& c) : Person5(n), company(c) {}
	void print() const {
		Person5::print();
		cout << "print() function in Employee2" << " is emplayed by " << company << endl;
	}
};
{% endhighlight %}
