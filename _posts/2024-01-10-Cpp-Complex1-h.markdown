---
layout: post
title:  "C++: Complex1.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Complex1.h   
`Complex1.h` : example of calculating complex number - integer // 복소수 계산 예제 - 정수   
   
```cpp
#pragma once

class Complex1 {
	double rPart, iPart;		// 복소수의 실수부 및 허수부
public:
	// 생성자
	Complex1(double r = 0, double i = 0) : rPart(r), iPart(i) {}
	Complex1 conj() const {
		return Complex1(rPart, -iPart);		// Complex1 클래스의 임시 객체 생성되고, 문장 실행 후 임시 객체 소멸됨
	}
	Complex1 add(const Complex1& c) const {
		return Complex1(rPart + c.rPart, iPart + c.iPart);		// Complex1 클래스의 임시 객체 생성되고, 문장 실행 후 임시 객체 소멸됨
	}
	Complex1 sub(const Complex1& c) const {
		return Complex1(rPart - c.rPart, iPart - c.iPart);		// Complex1 클래스의 임시 객체 생성되고, 문장 실행 후 임시 객체 소멸됨
	}
	Complex1 mul(const Complex1& c) const;		// 복소수 곱셈
	Complex1 div(const Complex1& c) const;		// 복소수 나눗셈
	void display() const;				// 복소수 값을 출력
};
```
