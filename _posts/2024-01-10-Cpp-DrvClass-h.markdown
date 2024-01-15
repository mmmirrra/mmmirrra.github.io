---
layout: post
title:  "C++: DrvClass.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - DrvClass.h   
   
// 가상함수로 정의된 소멸자를 가진 기초 클래스를 상속받는 상세 클래스 예제   
`DrvClass.h` : example of a detail class that inherits a base class with an destructor defined as a virtual function   
   
```cpp
#pragma once
#include "BaseClass.h"

class DrvClass : public BaseClass {		// 가상함수로 정의된 소멸자를 가진 기초 클래스를 상속받는 상세 클래스 예제
	int* ptD;
public:
	DrvClass(int n1, int n2) : BaseClass(n1) {
		cout << "DrvClass constructor Runs" << endl;
		ptD = new int[n2];
	}
	~DrvClass() override final {		// 기초 클래스의 소멸자가 가상함수이므로 파생 클래스의 소멸자도 가상함수가 됨. 기초 클래스의 소멸자가 가상함수가 아닌 경우 이 소멸자가 실행되지 않을 수 있음. 기초 클래스의 가상함수를 재정의했다는 것을 알리기 위해 override 키워드 사용. 가상함수를 다음 파생 클래스에서 더이상 재정의하지 못하게 하기 위해 final 키워드 사용
		cout << "DrvClass destructor Runs" << endl;
		delete[] ptD;
	}
};
```
