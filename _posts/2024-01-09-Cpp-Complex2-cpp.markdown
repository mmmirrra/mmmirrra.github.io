---
layout: post
title:  "C++: Complex2.cpp : etc sourceFile"
date:   2024-01-09 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - etc sourceFile - Complex2.cpp   
   
// 복소수 계산 예제 - 실수   
`Complex2.cpp` : example of calculating complex number - real number   
   
```cpp
#include <iostream>
#include "Complex2.h"
using namespace std;

Complex2 Complex2::operator + (const Complex2& c) const {	// 복소수 덧셈 연산자 다중정의
	cout << "Addition Operator Multiple Definition : ";
	// Complex2 tmp(*this);
	// tmp.rPart += c.rPart;
	// tmp.iPart += c.iPart;
	// return tmp;
	return Complex2(rPart + c.rPart, iPart + c.iPart);
}

Complex2 Complex2::operator + (double r) const {		// 복소수 덧셈 연산자 다중정의
	cout << "Addition Operator Multiple Definition : ";
	return Complex2(rPart + r, iPart);
}

Complex2& Complex2::operator += (const Complex2& c) {		// 복소수 복합 대입 연산자 다중정의
	cout << "Multiple Definition of Complex Substitutions Operator : ";
	rPart += c.rPart;
	iPart += c.iPart;
	return *this;
}

void Complex2::display() const {			// 복소수 값을 출력
	cout << "(" << rPart;
	if (iPart > 0)
		cout << "+j" << iPart;
	else if (iPart < 0)
		cout << "-j" << -iPart;
	cout << ")";
}

// 좌측 피연산자가 실수인 경우 덧셈 연산자 다중정의. Complex2 클래스에 속하지 않는 외부 연산자로 정의해야 함
Complex2 operator + (double r, const Complex2& c) {
	cout << "Multiple addition operator definition if left operand is real number : ";
	// return Complex2(r + c.rPart, c.iPart); -> private 멤버를 사용했기 때문에 오류 발생
	return Complex2(r + c.rPart, c.iPart);		// Complex2.h 파일에서 이 함수를 friend로 지정하였기 때문에 private 멤버를 자유롭게 사용할 수 있음
	// return Complex2(r + c.real(), c.imag());	// friend로 지정되어 있지 않은 경우 public 함수를 통해 private 멤버 값을 찾아올 수 있음
}

// 출력 연산자 다중정의. Complex2 클래스에 속하지 않는 외부 연산자로 정의해야 함
ostream& operator << (ostream& os, const Complex2& c) {
	cout << "Output operator multiple definition : ";
	os << "(" << c.rPart;		// 실수부 출력
	if (c.iPart > 0)		// 허수부 출력
		os << "+j" << c.iPart;
	else if (c.iPart < 0)
		os << "-j" << -c.iPart;
	os << ")";
	return os;
}
```
