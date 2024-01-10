---
layout: post
title:  "C++: Figure.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Figure.h   
`Figure.h` : abstract class - abstract class for class that can draw shapes // 추상 클래스 - 도형을 그릴 수 있는 클래스에 대한 추상 클래스   
   
```cpp
#pragma once
#include <string>
#include "GrAttrib.h"
using namespace std;

class Figure {						// 추상 클래스 - 도형 클래스
protected:							// 파생 클래스에서는 proteted 멤버를 직접 엑세스하여 자유롭게 사용할 수 있음
	GrAttrib attrib;				// 그래픽 속성
public:
	Figure(): attrib(curAttrib) {}						// 현재 그래픽 속성에 따라 도형 객체 생성
	void setLineColor(const string& c) {				// 선 색상 속성 지정
		attrib.setLineColor(c);
	}
	void setFillColor(const string& c) {				// 내부 영역 색상 속성 지정
		attrib.setFillColor(c);
	}
	virtual void move(double dx, double dy) = 0;		// 순수가상함수 - 도형의 이동
	virtual void scale(double s) = 0;					// 순수가상함수 - 원점 기준 크기조정
	virtual void draw() const = 0;						// 순수가상함수 - 그리기 멤버함수
};
```
