---
layout: post
title:  "C++: Pencils.cpp : etc sourceFile"
date:   2024-01-09 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - etc sourceFile - Pencils.cpp   
   
// ++ 연산자 전위 표기, 후위 표기 예제   
`Pencils.cpp` : example of prefix and postfix for ++ operator   
   
```cpp
#include <iostream>
#include "Pencils.h"
using namespace std;

Pencils& Pencils::operator ++ () {		// ++ 연산자 (전위 표기)
	cout << "++ operator (prefix) : ";
	if (++np >= 12)			// 낱개를 1 증가시킴. 결과가 12보다 크면
		++dozens, np = 0;		// 타 수를 1 증가시키고, 낱개는 0
	return *this;				// 증가된 결과를 반환
}

Pencils Pencils::operator ++ (int) {		// ++ 연산자 (후위 표기)
	cout << "++ operator (postfix) : ";
	Pencils tmp(*this);			// 현재 객체를 보존
	if (++np >= 12)			// 낱개를 1 증가시킴. 결과가 12보다 크면
		++dozens, np = 0;		// 타 수를 1 증가시키고, 낱개는 0
	return tmp;				// 보존된 객체를 반환
}

void Pencils::display() const {
	if (dozens) {
		cout << dozens << "bundles ";
		if (np) cout << np << "individuals ";
		cout << endl;
	}
	else
		cout << np << "individuals " << endl;
}
```
