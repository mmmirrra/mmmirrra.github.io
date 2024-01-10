---
layout: post
title:  "C++: Circle.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Circle.h   
`Circle.h` : detail class - example of a circle class drawing a circle // 상세 클래스 - 원을 그리는 원 클래스 예제   
   
```cpp
#pragma once
#include <iostream>
#include <string>
#include "Figure.h"
using namespace std;

class Circle : public Figure {		// 상세 클래스 - 원 클래스
	double cx, cy;					// 원의 중심 좌표
	double radius;					// 원의 반경
public:
	Circle(double x, double y, double r) : cx(x), cy(y), radius(r) {}			// 생성자 - 현재의 그래픽 속성에 따라 원 객체 생성. (x, y)는 중심좌표. r은 반경
	void move(double dx, double dy) {											// 순수가상함수를 재정의 - 원의 이동 - 원의 중심좌표를 (dx, dy) 만큼 이동
		cx += dx;
		cy += dy;
	}
	void scale(double s) {														// 순수가상함수를 재정의 - 원점 기준 크기 변경 - 좌표 원점을 기준으로 s배 크기 조정
		cx *= s;
		cy *= s;
		radius *= s;
	}
	void draw() const {															// 순수가상함수를 재정의 - 원 그리기 멤버함수
		cout << "Draw a circle" << endl;
		cout << "(" << cx << ", " << cy << ")에서부터 ";
		cout << radius << "만큼 떨어진 모든 점들을 ";
		cout << attrib.getLineColor() << "으로 그리고" << endl;
		cout << "내부를 " << attrib.getFillColor();
		cout << "으로 채운다." << endl;
	}
};
```
