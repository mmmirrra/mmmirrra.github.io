---
layout: post
title:  "C++: IntArray1.cpp : etc sourceFile"
date:   2024-01-09 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - etc sourceFile - IntArray1.cpp   
   
// 사용자 정의 객체 오류 처리 예제   
`IntArray1.cpp` : example of error handling of a custom object   
   
```cpp
#include "IntArray1.h"
using namespace std;

IntArray1::IntArray1(int s) : size(s) {		// 생성자
	buf = new int[s];
	memset(buf, 0, sizeof(int) * s);
}

int& IntArray1::operator [] (int offset) {		// 첨자 연산자
	if (offset < 0 || offset >= size)		// 예외조건 검사 - 정상적인 범위인지 확인
		throw BadIndex1(offset);		// 예외객체 BadIndex 객체를 생성 및 전달
	return buf[offset];
}
```
