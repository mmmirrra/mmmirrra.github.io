---
layout: post
title:  "C++: IntArray1.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - IntArray1.h   
// 사용자 정의 객체 오류 처리 예제 - 오류가 발생한 첨자 리턴   
`IntArray1.h` : example of error handling of a custom object - returns a subscript with an error   
   
```cpp
#pragma once
#include <ostream>
using namespace std;

const int DefaultSize = 10;
class IntArray1 {		// 사용자 정의 객체 오류 처리 예제 - 오류가 발생한 첨자 리턴
	int* buf;
	int size;
public:
	IntArray1(int s = DefaultSize);				// 생성자
	virtual ~IntArray1() { delete[] buf; }		// 소멸자 - 가상
	int& operator [] (int offset);			// 첨자 연산자 - 첨자가 범위내에 있는지 확인
	const int& operator [] (int offset) const;		// 첨자 연산자 - 첨자가 범위내에 있는지 확인
	int getSize() const { return size; }
	friend ostream& operator << (ostream&, IntArray1&);
	class BadIndex1 {		// exception class
	public:
		int wrongIndex;
		BadIndex1(int n) : wrongIndex(n) {}
	};
};
```
