---
layout: post
title:  "C++: CharStack.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - CharStack.h   
   
// 스택 공간 확인 예제   
`CharStack.h` : example of verifying stack space   
   
```cpp
#pragma once

class CharStack {		// 스택 공간 확인 예제
	enum {size=20};
	int top;
	char buf[size];
public:
	CharStack() : top{ size } {}
	bool chkEmpty() const {
		return top == size;
	}
	bool chkFull() const {
		return !top;
	}
	bool push(char ch);
	char pop();
};
```
