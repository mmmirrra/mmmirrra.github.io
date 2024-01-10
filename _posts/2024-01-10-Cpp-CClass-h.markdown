---
layout: post
title:  "C++: CClass.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - CClass.h   
`CClass.h` : detail class - able to create object // 상세 클래스 - 객체를 만들 수 있음   
   
{% highlight cpp %}
#pragma once
#include <iostream>
#include "AClass.h"
using namespace std;

class CClass : public AClass {					// 상세 클래스 - 순수가상함수를 포함하지 않는 클래스. 상위 클래스의 순수가상함수는 재정의 필요. 객체를 만들 수 있음. ex. CClass objC;
public:
	void vf() const {							// 상위 클래스의 순수가상함수를 재정의 함
		cout << "Implementing a Pure Virtual Function" << endl;
	}
	void f2() const {
		cout << "Consrete" << endl;
	}
};
{% endhighlight %}
