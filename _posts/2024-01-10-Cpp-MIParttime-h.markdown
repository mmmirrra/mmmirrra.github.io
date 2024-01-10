---
layout: post
title:  "C++: MIParttime.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - MIParttime.h   
`MIParttime.h` : class that receive multiple inheritances - multiple inheritance of class in the MIEployee.h and MISstudent.h files // 클래스를 다중상속 받는 클래스 - MIEmployee.h 와 MIStudent.h 파일의 클래스를 다중상속   
   
```cpp
#pragma once
#include <string>
#include "MIStudent.h"
#include "MIEmployee.h"
using namespace std;

class Parttime1 : public Student4, public Employee1 {	// 클래스를 다중상속 받는 클래스 - Student4와 Employee를 모두 상속받음
public:
	Parttime1(const string& s, const string& c) : Student4(s), Employee1(c) {}		// 생성자
};
```
