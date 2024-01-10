---
layout: post
title:  "C++: IntClass2.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - IntClass2.h   
`IntClass2.h` : postfix ++ operator multiple definitions // 후위 표기 ++ 연산자 다중정의   
   
{% highlight cpp %}
#pragma once

class IntClass2 {
	int a;
public:
	IntClass2(int n = 0) : a(n) {}		// 생성자
	IntClass2 operator ++ (int) {		// 후위 표기 ++ 연산자 다중정의
		cout << "postfix ++ operator multiple definitions : ";
		IntClass2 tmp(*this);
		++a;
		return tmp;
	}
	int getValue() const { return a; }
};
{% endhighlight %}
