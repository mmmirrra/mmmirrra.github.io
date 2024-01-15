---
layout: post
title:  "C++: Triangle.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Triangle.h   
   
// 상세 클래스 - 삼각형을 그리는 삼각형 클래스 예제   
`Triangle.h` : detail class - example of a triangle class drawing a triangle   
   
```cpp
#pragma once
#include <iostream>
#include <string>
#include "Figure.h"
using namespace std;

class Triangle : public Figure {	// 상세 클래스 - 삼각형 클래스
	double x1, y1;			// 삼각형의 꼭짓점 좌표
	double x2, y2;
	double x3, y3;
public:
	Triangle(double v[3][2]) {	// 생성자 - 현재의 그래픽 속성에 따라 삼각형 객체 생성. v는 세 개의 꼭지점 좌표 배열임
		x1 = v[0][0];		// 매개변수로 전달된 2차원 배열로 초기화 함
		y1 = v[0][1];
		x2 = v[1][0];
		y2 = v[1][1];
		x3 = v[2][0];
		y3 = v[2][1];
	}
	void move(double dx, double dy) {	// 순수가상함수를 재정의 - 삼각형의 이동 - 삼각형을 (dx, dy)만큼 이동 - 세 꼭지점 좌표르 (dx, dy)만큼 이동
		x1 += dx;
		y1 += dy;
		x2 += dx;
		y2 += dy;
		x3 += dx;
		y3 += dy;
	}
	void scale(double s) {			// 순수가상함수를 재정의 - 원점 기준 크기 변경 - 삼각형을 원점 기준으로 s배 크기 조정 - 세 꼭지점 좌표를 s배 만큼 조정
		x1 *= s;
		y1 *= s;
		x2 *= s;
		y2 *= s;
		x3 *= s;
		y3 *= s;
	}
	void draw() const {			// 순수가상함수를 재정의 - 삼각형 그리기 멤버함수
		cout << "Draw a triangle" << endl;
		cout << "(" << x1 << ", " << y1 << "), ";
		cout << "(" << x2 << ", " << y2 << "), ";
		cout << "(" << x3 << ", " << y3 << ")의 좌표를 잇는 선분을 ";
		cout << attrib.getLineColor() << "으로 그리고" << endl;
		cout << "내부를 " << attrib.getFillColor();
		cout << "으로 채운다." << endl;
	}
};
```
