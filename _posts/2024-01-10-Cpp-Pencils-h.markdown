---
layout: post
title:  "C++: Pencils.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Pencils.h   
// ++연산자 전위 표기, 후위 표기 예제 - 연필 묶음과 낱개의 개수 계산   
`Pencils.h` : example of prefix and postfix for ++ operator - calculate the number of pencil bundles and individuals   
   
```cpp
#pragma once

class Pencils {		// ++연산자 전위 표기, 후위 표기 예제 - 연필 묶음과 낱개의 개수 계산
	int dozens;		// 타
	int np;			// 낱개
public:
	Pencils() : dozens(0), np(0) {};	// 생성자
	Pencils(int n) {			// 생성자
		dozens = n / 12;		// 몫 구하기
		np = n % 12;			// 나머지 구하기
	}
	Pencils(int d, int n) : dozens(d), np(n) {}	// 생성자
	Pencils& operator ++ ();			// ++ 연산자 (전위 표기)
	Pencils operator ++ (int);			// ++ 연산자 (후위 표기)
	void display() const;
};
```
