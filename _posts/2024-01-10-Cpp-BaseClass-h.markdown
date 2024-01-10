---
layout: post
title:  "C++: BaseClass.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - BaseClass.h   
`BaseClass.h` : example of creating a virtual function of a destructor in a base class // 기초 클래스의 소멸자를 가상함수로 만드는 예제   
   
```cpp
#pragma once

class BaseClass {			// 기초 클래스의 소멸자를 가상함수로 만드는 예제
	int* ptB;
public:
	BaseClass(int n) {
		cout << "BaseClass constructor Runs" << endl;
		ptB = new int[n];
	}
	virtual ~BaseClass() {		// 기초 클래스의 소멸자를 가상함수로 만듦. 가상함수로 만들지 않은 경우 파생 클래스의 소멸자가 실행되지 않을 수 있음
		cout << "BaseClass destructor Runs" << endl;
		delete[] ptB;
	}
};
```
