---
layout: post
title:  "C++: Counter.cpp : etc sourceFile"
date:   2024-01-09 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - etc sourceFile - Counter.cpp   
// 헤더파일 외부에 정의하는 함수 예제   
`Counter.cpp` : example of a function defined outside of a header file   
   
```cpp
#include <iostream>
#include "Counter.h"

using namespace std;

void Counter::f() {		// 헤더 파일 외부에 함수 정의 예제
	cout << "function f(), a function created separately by Counter.h " << endl;
};
```
