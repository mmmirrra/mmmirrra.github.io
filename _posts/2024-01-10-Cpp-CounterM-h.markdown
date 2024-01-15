---
layout: post
title:  "C++: CounterM.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - CounterM.h   
   
// 카운터가 최대값에 도달했을 때 0으로 리셋되는 숫자 누적 계산기   
`CounterM.h` : a numeric accumulator that resets to zero when the counter reaches its maximum value   
   
```cpp
#pragma once COUNTERM_H_INCLUDED
#include <iostream>

class CounterM {		// 카운터가 최대값에 도달했을 때 0으로 리셋되는 숫자 누적 계산기
	const int maxValue;
	int value;
public:
	CounterM(int mVal) : maxValue{ mVal }, value{ 0 } { }
	~CounterM() {
		std::cout << "Bye~~~" << std::endl;
	}
	void reset() {
		value = 0;
	}
	void count() {
		value = value < maxValue ? ++value : 0;
	}
	int getValue() const {
		return value;
	}
};
```
