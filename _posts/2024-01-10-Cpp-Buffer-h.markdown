---
layout: post
title:  "C++: Buffer.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Buffer.h   
// 템플릿 생성 시 매개변수로 자료형과 정수를 받는 예제   
`Buffer.h` : example of receiving data types and integer as parameters when creating a template   
   
```cpp
#pragma once

template <typename T, int size>		// 템플릿 생성 시 매개변수로 자료형과 정수를 받는 예제
class Buffer {
	T buf[size];
};
```
