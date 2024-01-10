---
layout: post
title:  "C++: GrAttrib.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - GrAttrib.h   
`GrAttrib.h` : abstract class - abstract class for class that specify graphic properties of a shapes // 추상 클래스 - 도형의 그래픽 속성을 지정할 수 있는 클래스에 대한 추상 클래스   
   
```cpp
#pragma once
#include <string>
using namespace std;

class GrAttrib {					// 추상 클래스 - 도형의 그래픽 속성 클래스
	string lineColor;				// 선 색 속성
	string fillColor;				// 내부 영역 색 속성
public:
	GrAttrib() : lineColor("Black"), fillColor("White") {}								// 그래픽 속성 객체 생성자 - 디폴트 생성자
	GrAttrib(const string& lc, const string& fc) : lineColor(lc), fillColor(fc) {}		// 그래픽 속성 객체 생성자 - 지정된 색상으로 초기화하는 생성자
	void setLineColor(const string& lc) {												// 속성 지정 멤버함수 - 선 색상 지정
		lineColor = lc;
	}
	void setFillColor(const string& fc) {												// 속성 지정 멤버함수 - 내부 영역 색상 지정
		fillColor = fc;
	}
	string getLineColor() const {														// 속성 값을 읽는 멤버함수 - 선 색상 읽음
		return lineColor;
	}
	string getFillColor() const {														// 속성 값을 읽는 멤버함수 - 내부 영역 색상 읽음
		return fillColor;
	}
};

extern GrAttrib curAttrib;			// 전역변수 선언임. 실제 정의는 다른 파일 어딘가에 있어야 함. 현재 속성을 나타내는 전역 객체이므로 소스파일 내에서 어디서든 사용 가능. extern은 전역 객체임을 알리는 키워드임. 현재 속성을 프로그램이 끝날때까지 사용할 수 있고, 중간에 값을 변경할 수도 있음
```
