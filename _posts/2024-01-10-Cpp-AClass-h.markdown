---
layout: post
title:  "C++: AClass.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - AClass.h   
// 추상 클래스 - 객체를 만들 수 없음   
`AClass.h` : abstract class - unable to create object   
   
```cpp
#pragma once
#include <iostream>
using namespace std;

class AClass {		// 추상 클래스 - 객체를 만들 수 없음. ex. AClass objA; 컴파일 시 오류 발생
public:
	virtual void vf() const = 0;		// 순수가상함수
	void f1() const {			// 일반함수
		cout << "Abstract" << endl;
	}
};
```
