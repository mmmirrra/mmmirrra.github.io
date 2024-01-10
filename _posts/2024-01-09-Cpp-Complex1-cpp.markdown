---
layout: post
title:  "C++: Complex1.cpp : etc sourceFile"
date:   2024-01-09 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - etc sourceFile - Complex1.cpp   
`Complex1.cpp` : example of calculating complex number - integer // 복소수 계산 예제 - 정수   
   
```cpp
#include <iostream>
#include "Complex1.h"
using namespace std;

Complex1 Complex1::mul(const Complex1& c) const {		// 복소수 곱셈
	double r = rPart * c.rPart - iPart * c.iPart;
	double i = rPart * c.iPart + iPart + c.rPart;
	return Complex1(r, i);
}

Complex1 Complex1::div(const Complex1& c) const {		// 복소수 나눗셈
	double d = c.rPart * c.rPart + c.iPart * c.iPart;
	Complex1 c1 = mul(c.conj());
	return Complex1(c1.rPart / d, c1.iPart / d);
}

void Complex1::display() const {		// 복소수 값을 출력
	cout << "(" << rPart;
	if (iPart > 0)
		cout << "+j" << iPart;
	else if (iPart < 0)
		cout << "-j" << -iPart;
	cout << ")";
}
```
