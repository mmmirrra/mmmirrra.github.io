---
layout: post
title:  "C++: IntArray2.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - IntArray2.h   
`IntArray2.h` : example of error handling of a custom object - use exception() // 사용자 정의 객체 오류 처리 예제 - exception() 사용   
   
```cpp
#pragma once
#include <ostream>
#include <exception>
using namespace std;

const int DefaultSize = 10;
class IntArray2 {		// 사용자 정의 객체 오류 처리 예제 - exception() 사용
	int* buf;
	int size;
public:
	IntArray2(int s = DefaultSize);				// 생성자
	virtual ~IntArray2() { delete[] buf; }		// 소멸자 - 가상
	int& operator [] (int offset);			// 첨자 연산자 - 첨자가 범위내에 있는지 확인
	const int& operator [] (int offset) const;		// 첨자 연산자 - 첨자가 범위내에 있는지 확인
	int getSize() const { return size; }
	friend ostream& operator << (ostream&, IntArray2&);
	class BadIndex2 : public exception {			// exception 클래스의 파생클래스오 BadIndex2 class를 만듦
	public:
		int wrongIndex;
		BadIndex2(int n) : wrongIndex(n), exception() {}
		const char* what() const {			// what은 exception의 멤버함수임. 재정의함 
			return "Array Exception::";
		}
	};
};
```
