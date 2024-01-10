---
layout: post
title:  "C++: Complex2.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Complex2.h   
`Complex2.h` : example of calculating complex number - real numbers // 복소수 계산 예제 - 실수   
   
```cpp
#pragma once
#include <iostream>
using namespace std;

class Complex2 {
	double rPart, iPart;		// 복소수의 실수부 및 허수부
public:
	Complex2(double r = 0, double i = 0) : rPart(r), iPart(i) {};		// 생성자
	Complex2 operator + (const Complex2& c) const;		// 덧셈 연산자 다중정의
	Complex2 operator + (double r) const;		// 덧셈 연산자 다중정의
	Complex2& operator += (const Complex2& c);		// 복합 대입 연산자 다중정의
	void display() const;		// 복소수 값을 출력

	double real() const {
		return rPart;		// 실수부의 값 반환. 이게 없으면 private 인 rPart를 외부 함수에서 읽을 수 없음
	}
	double imag() const {
		return iPart;		// 허수부의 값 반환. 이게 없으면 private 인 iPart를 외부 함수에서 읽을 수 없음
	}

	friend Complex2 operator + (double r, const Complex2& c);		// 좌측 피연산자가 실수인 경우 덧셈 연산자 다중정의. 외부 연산자 원형을 friend로 정의. private 인 rPart, iPart를 자유롭게 사용할 수 있음

	friend ostream& operator << (ostream& os, const Complex2& c);		// 출력 연산자 다중정의. 외부 연산자 원형을 friend로 정의. private 인 rPart, iPart를 자유롭게 사용할 수 있음
};
```
