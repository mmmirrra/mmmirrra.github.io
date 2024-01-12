---
layout: post
title:  "C++: IntClass1.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - IntClass1.h   
// 전위 표기 ++ 연산자 다중정의   
`IntClass1.h` : prefix ++ operator multiple definitions   
   
```cpp
#pragma once

class IntClass1 {
	int a;
public:
	IntClass1(int n = 0) : a(n) {}		// 생성자
	IntClass1& operator ++ () {		// 전위 표기 ++ 연산자 다중정의
		cout << "prefix ++ operator multiple definitions : ";
		++a;
		return *this;
	}
	int getValue() const { return a; }
};
```
