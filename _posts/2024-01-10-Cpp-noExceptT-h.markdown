---
layout: post
title:  "C++: noExceptT.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - noExceptT.h   
`noExceptT.h` : example of a noexcept declaration - a declaration not to cause exceptions // noexcept 선언 예제 - 예외를 일으키지 않는다는 선언   
   
{% highlight cpp %}
#pragma once
#include "StackT.h"

template <typename T>
T max(const Stack<T>& v) noexcept {			// noexcept는 이 함수가 예외를 일으키지 않는다는 선언 - 이 함수를 호출하여 사용하는 곳에서도 예외 처리를 할 필요가 없음
	auto p = v.begin();
	T m = *p++;
	for (; p != v.end(); p++)
		if (m < *p) m = *p;
	return m;
};
{% endhighlight %}
