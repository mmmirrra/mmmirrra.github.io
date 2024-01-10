---
layout: post
title:  "C++: SafeIntArray.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - SafeIntArray.h   
`SafeIntArray.h` : example of verifying that subscripts are accessible by data storage space // 데이터 저장공간에 따른 첨자 접근 가능여부를 확인하는 예제   
   
```cpp
#pragma once
#include <iostream>

class SafeIntArray {									// 데이터 저장공간에 따른 첨자 접근 가능여부를 확인하는 예제
	int limit;											// 원소의 개수
	int* arr;											// 데이터 저장공간
public:
	SafeIntArray(int n) : limit(n) {					// 생성자
		arr = new int[n];								// 데이터 저장공간 할당
	}
	~SafeIntArray() {									// 소멸자
		delete[] arr;
	}
	int size() const {
		return limit;									// 저장 가능한 원소 개수 리턴
	}
	// 첨자 연산자를 다중정의 할 때는 값을 바꿀 수 있는 첨자 연산자와 값을 읽기만 하는 첨자 연산자를 모두 구현해야 함
	int& operator [] (int i) {							// 값을 바꿀 수 있는(대입할 수 있는) 첨자 연산자 - i번 원소를 반환하는 멤버함수
		if (i < 0 || i >= limit) {
			std::cout << "Exit the program because the subscript is out of range.";
			exit(EXIT_FAILURE);
		}
		return arr[i];									// i번 원소 반환 - 참조를 전달
	}
	int operator [] (int i) const {						// 값을 읽기만 하는 첨자 연산자 - i번 원소를 반환하는 멤버함수
		if (i < 0 || i >= limit) {
			std::cout << "Exit the program because the subscript is out of range.";
			exit(EXIT_FAILURE);
		}
		return arr[i];									// i번 원소 반환 - 값을 전달
	}
};
```
