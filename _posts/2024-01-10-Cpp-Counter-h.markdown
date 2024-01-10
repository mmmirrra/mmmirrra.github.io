---
layout: post
title:  "C++: Counter.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Counter.h   
`Counter.h` : example of a function defined outside of a header file - a numeric accumulator that increases the number when clicked // 헤더파일 외부에 정의하는 함수 예제 - 클릭 시 숫자가 올라가는 숫자 누적 계산기   
   
```cpp
// 동일한 헤더파일이 여러번 생기는것을 방지하기 위해 #ifndef를 씀 - #pragma once 도 많이씀
#ifndef COUNTER_H_INCLUDED
#define COUNTER_H_INCLUDED

class Counter {		// 클릭 시 숫자가 올라가는 숫자 누적 계산기
	int value;		// private 데이터멤버
public:
	Counter() : value{ 0 } {		// value{ 0 } 처럼 초기화 하는 경우 const 데이터 멤버도 초기화 가능
//	Counter() {		// 생성자에는 매개변수를 넣어줄 수 있음
//		value = 0;		// 이건 대입 연산자이므로 const 데이터 멤버는 초기화 불가능함
		std::cout << "Initialize value to 0 in the constructor function of Counter Class" << std::endl;
	}
	~Counter() {		// 소멸자에는 매개변수를 넣어줄 수 없음
		std::cout << "Bye~~~" << std::endl;
	}
	void reset() {
		value = 0;
	}
	void count() {
		++value;
	}
	int getValue() const {
		return value;
	}
	void f();		// 외부에 정의하는 함수 원형 예제
};

#endif // COUNTER_H_INCLUDED
```
