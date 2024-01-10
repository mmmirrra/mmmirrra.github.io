---
layout: post
title:  "C++: BaseC.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - BaseC.h   
`BaseC.h` : example of a member's scope of use by permission // 권한에 따른 멤버 사용 범위 예제   
   
```cpp
#pragma once

class BaseC {		// 권한에 따른 멤버 사용 범위 예제
	int a;		// private 멤버
protected:
	int b;		// protected 멤버
public:
	int c;		// public 멤버
	int geta() const {
		return a;
	}
	void set(int x, int y, int z) {
		a = x;
		b = y;
		c = z;
	}
};
```
