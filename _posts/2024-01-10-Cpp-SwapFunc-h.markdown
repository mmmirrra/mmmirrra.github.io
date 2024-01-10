---
layout: post
title:  "C++: SwapFunc.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - SwapFunc.h   
`SwapFunc.h` : example of a function template - a function that exchanges values // 함수 템플릿 예제 - 값을 서로 교환하는 함수   
   
```cpp
#pragma once
#include <iostream>
#include <utility>
using namespace std;

template <typename ANY>		// 함수 템플릿 선언
void swapFT(ANY& a, ANY& b) {		// 값을 서로 교환하는 함수
	ANY temp = move(a);		// rvalue 참조를 사용하여 이동 - 이 함수 템플릿 매개변수를 통해 전달되는 전달자 클래스는 이동 대입 연산자가 정의되어 있어야 함
	a = move(b);
	b = move(temp);
	cout << "Run swapFT function template - exchange two values" << endl;
};
```
