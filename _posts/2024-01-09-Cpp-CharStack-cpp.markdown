---
layout: post
title:  "C++: CharStack.cpp : etc sourceFile"
date:   2024-01-09 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - etc sourceFile - CharStack.cpp   
// 스택 공간 확인 예제   
`CharStack.cpp` : example of verifying stack space   
   
```cpp
#include <iostream>
#include "CharStack.h"
using namespace std;

bool CharStack::push(char ch)
{
	if (chkFull()) {
		cout << "The stack is full." << endl;
		return false;
	}
	buf[--top] = ch;		// 스택에 공간이 있으면 저장
	return true;
}

char CharStack::pop() {
	if (chkEmpty()) {
		cout << "There is no data in the stack." << endl;
		return 0;
	}
	return buf[top++];		// top 위치의 데이터 반환
}
```
