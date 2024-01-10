---
layout: post
title:  "C++: Greater.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Greater.h   
`Greater.h` : class with function objects - object that can be used as function // 함수객체를 포함한 클래스 - 함수처럼 사용될 수 있는 객체   
   
```cpp
#pragma once

template<typename T>
class GREATER {		// 함수객체를 포함한 클래스: 함수처럼 사용될 수 있는 객체 - 함수객체처럼 사용하기 위해서는 클래스에 () 연산자가 다중정의되어 있어야 함
public:
	bool operator () (const T& a, const T& b) const {		// 함수를 호출하는 () 연산자를 다중정의 - 인라인 inline 함수임. 일반적인 인라인 함수는 함수 포인터를 만들 수 없으나 함수객체 형태로 전달하면 객체의 멤버함수인 인라인 함수를 호출하는 것처럼 만들어줌. 인라인 함수를 호출하면 일반함수를 호출하는 것에 비해 호출 절차가 매우 간단함
	return a > b;		// 내림차순
	}
};
```
