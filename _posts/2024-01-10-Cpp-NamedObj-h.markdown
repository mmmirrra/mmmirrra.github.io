---
layout: post
title:  "C++: NamedObj.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - NamedObj.h   
`NamedObj.h` : example of how constructor and destructor work // 생성자, 소멸자 동작 예제   
   
{% highlight cpp %}
#pragma once NAMEDOBJ_H_INCLOUDED
#include <iostream>
using namespace std;

class NamedObj {						// 생성자, 소멸자 동작 예제
	char* name;
	int id;
	static int nConstr;
	static int nDestr;
public:
	NamedObj(const char* s);
	~NamedObj();
	void display() const {
		cout << "ID : " << id << " --> name : " << name << endl;
	}
	static int nObj() {
		return nConstr - nDestr;
	}
};
{% endhighlight %}
