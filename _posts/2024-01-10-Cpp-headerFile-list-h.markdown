---
layout: post
title:  "C++: headerFile list : .h"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - .h   
   
// 추상 클래스 - 객체를 만들 수 없음   
`AClass.h` : Abstract Class - Unable to create object   
   
```cpp
#pragma once
#include <iostream>
using namespace std;

class AClass {		// 추상 클래스 - 객체를 만들 수 없음. e.g. AClass objA; 컴파일 시 오류 발생
public:
	virtual void vf() const = 0;		// 순수가상함수
	void f1() const {			// 일반함수
		cout << "Abstract" << endl;
	}
};
```
   
<br />
// 권한에 따른 멤버 사용 범위 예제   
`BaseC.h` : Example of a Member's scope of use by permission   
   
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
   
<br />
// 기초 클래스의 소멸자를 가상함수로 만드는 예제   
`BaseClass.h` : Example of creating a Virtual Function of a Destructor in a Base Class   
   
```cpp
#pragma once

class BaseClass {			// 기초 클래스의 소멸자를 가상함수로 만드는 예제
	int* ptB;
public:
	BaseClass(int n) {
		cout << "BaseClass constructor Runs" << endl;
		ptB = new int[n];
	}
	virtual ~BaseClass() {		// 기초 클래스의 소멸자를 가상함수로 만듦. 가상함수로 만들지 않은 경우 파생 클래스의 소멸자가 실행되지 않을 수 있음
		cout << "BaseClass destructor Runs" << endl;
		delete[] ptB;
	}
};
```
   
<br />
// 템플릿 생성 시 매개변수로 자료형과 정수를 받는 예제   
`Buffer.h` : Example of receiving data types and integer as parameters when creating a template   
   
```cpp
#pragma once

template <typename T, int size>		// 템플릿 생성 시 매개변수로 자료형과 정수를 받는 예제
class Buffer {
	T buf[size];
};
```
   
<br />
// 상세 클래스 - 객체를 만들 수 있음   
`CClass.h` : Detail Class - Able to create object   
   
```cpp
#pragma once
#include <iostream>
#include "AClass.h"
using namespace std;

class CClass : public AClass {	// 상세 클래스 - 순수가상함수를 포함하지 않는 클래스. 상위 클래스의 순수가상함수는 재정의 필요. 객체를 만들 수 있음. e.g. CClass objC;
public:
	void vf() const {		// 상위 클래스의 순수가상함수를 재정의 함
		cout << "Implementing a Pure Virtual Function" << endl;
	}
	void f2() const {
		cout << "Consrete" << endl;
	}
};
```
   
<br />
// 스택 공간 확인 예제   
`CharStack.h` : Example of verifying stack space   
   
```cpp
#pragma once

class CharStack {		// 스택 공간 확인 예제
	enum { size=20 };
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
   
<br />
// 상세 클래스 - 원을 그리는 원 클래스 예제   
`Circle.h` : Detail Class - Example of a Circle Class drawing a Circle   
   
```cpp
#pragma once
#include <iostream>
#include <string>
#include "Figure.h"
using namespace std;

class Circle : public Figure {		// 상세 클래스 - 원 클래스
	double cx, cy;				// 원의 중심 좌표
	double radius;				// 원의 반경
public:
	Circle(double x, double y, double r) : cx(x), cy(y), radius(r) {}	// 생성자 - 현재의 그래픽 속성에 따라 원 객체 생성. (x, y)는 중심좌표. r은 반경
	void move(double dx, double dy) {		// 순수가상함수를 재정의 - 원의 이동 - 원의 중심좌표를 (dx, dy) 만큼 이동
		cx += dx;
		cy += dy;
	}
	void scale(double s) {				// 순수가상함수를 재정의 - 원점 기준 크기 변경 - 좌표 원점을 기준으로 s배 크기 조정
		cx *= s;
		cy *= s;
		radius *= s;
	}
	void draw() const {				// 순수가상함수를 재정의 - 원 그리기 멤버함수
		cout << "Draw a circle" << endl;
		cout << "(" << cx << ", " << cy << ")에서부터 ";
		cout << radius << "만큼 떨어진 모든 점들을 ";
		cout << attrib.getLineColor() << "으로 그리고" << endl;
		cout << "내부를 " << attrib.getFillColor();
		cout << "으로 채운다." << endl;
	}
};
```
   
<br />
// 복소수 계산 예제 - 정수   
`Complex1.h` : Example of calculating complex number - Integer   
   
```cpp
#pragma once

class Complex1 {
	double rPart, iPart;		// 복소수의 실수부 및 허수부
public:
	// 생성자
	Complex1(double r = 0, double i = 0) : rPart(r), iPart(i) {}
	Complex1 conj() const {
		return Complex1(rPart, -iPart);		// Complex1 클래스의 임시 객체 생성되고, 문장 실행 후 임시 객체 소멸됨
	}
	Complex1 add(const Complex1& c) const {
		return Complex1(rPart + c.rPart, iPart + c.iPart);	// Complex1 클래스의 임시 객체 생성되고, 문장 실행 후 임시 객체 소멸됨
	}
	Complex1 sub(const Complex1& c) const {
		return Complex1(rPart - c.rPart, iPart - c.iPart);	// Complex1 클래스의 임시 객체 생성되고, 문장 실행 후 임시 객체 소멸됨
	}
	Complex1 mul(const Complex1& c) const;			// 복소수 곱셈
	Complex1 div(const Complex1& c) const;			// 복소수 나눗셈
	void display() const;					// 복소수 값을 출력
};
```
   
<br />
// 복소수 계산 예제 - 실수   
`Complex2.h` : Example of calculating complex number - Real Number   
   
```cpp
#pragma once
#include <iostream>
using namespace std;

class Complex2 {
	double rPart, iPart;		// 복소수의 실수부 및 허수부
public:
	Complex2(double r = 0, double i = 0) : rPart(r), iPart(i) {};		// 생성자
	Complex2 operator + (const Complex2& c) const;			// 덧셈 연산자 다중정의
	Complex2 operator + (double r) const;					// 덧셈 연산자 다중정의
	Complex2& operator += (const Complex2& c);				// 복합 대입 연산자 다중정의
	void display() const;							// 복소수 값을 출력

	double real() const {
		return rPart;		// 실수부의 값 반환. 이게 없으면 private 인 rPart를 외부 함수에서 읽을 수 없음
	}
	double imag() const {
		return iPart;		// 허수부의 값 반환. 이게 없으면 private 인 iPart를 외부 함수에서 읽을 수 없음
	}

	friend Complex2 operator + (double r, const Complex2& c);		// 좌측 피연산자가 실수인 경우 덧셈 연산자 다중정의. 외부 연산자 원형 prototype 을 friend로 정의. private 인 rPart, iPart를 자유롭게 사용할 수 있음

	friend ostream& operator << (ostream& os, const Complex2& c);	// 출력 연산자 다중정의. 외부 연산자 원형 prototype 을 friend로 정의. private 인 rPart, iPart를 자유롭게 사용할 수 있음
};
```
   
<br />
// 헤더파일 외부에 정의하는 함수 예제 - 클릭 시 숫자가 올라가는 숫자 누적 계산기   
`Counter.h` : Example of a function defined outside of a header file - a numeric accumulator that increases the number when clicked   
   
```cpp
// 동일한 헤더파일이 여러번 생기는것을 방지하기 위해 #ifndef를 씀 - #pragma once 도 많이씀
#ifndef COUNTER_H_INCLUDED
#define COUNTER_H_INCLUDED

class Counter {		// 클릭 시 숫자가 올라가는 숫자 누적 계산기
	int value;		// private 데이터멤버
public:
	Counter() : value{ 0 } {		// value{ 0 } 처럼 초기화 하는 경우 const 데이터 멤버도 초기화 가능
//	Counter() {				// 생성자에는 매개변수를 넣어줄 수 있음
//		value = 0;			// 이건 대입 연산자이므로 const 데이터 멤버는 초기화 불가능함
		std::cout << "Initialize value to 0 in the constructor function of Counter Class" << std::endl;
	}
	~Counter() {				// 소멸자에는 매개변수를 넣어줄 수 없음
		std::cout << "Bye~~~" << std::endl;
	}
	void reset() {
		value = 0;
	}
	void count() {
		++value;
	}
	int getValue() const {
		return value;
	}
	void f();		// 외부에 정의하는 함수 원형 prototype 예제
};

#endif // COUNTER_H_INCLUDED
```
   
<br />
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
   
<br />
// 가상함수로 정의된 소멸자를 가진 기초 클래스를 상속받는 상세 클래스 예제   
`DrvClass.h` : Example of a Detail Class that inherits a Base Class with an Destructor defined as a Virtual Function   
   
```cpp
#pragma once
#include "BaseClass.h"

class DrvClass : public BaseClass {		// 가상함수로 정의된 소멸자를 가진 기초 클래스를 상속받는 상세 클래스 예제
	int* ptD;
public:
	DrvClass(int n1, int n2) : BaseClass(n1) {
		cout << "DrvClass constructor Runs" << endl;
		ptD = new int[n2];
	}
	~DrvClass() override final {		// 기초 클래스의 소멸자가 가상함수이므로 파생 클래스의 소멸자도 가상함수가 됨. 기초 클래스의 소멸자가 가상함수가 아닌 경우 이 소멸자가 실행되지 않을 수 있음. 기초 클래스의 가상함수를 재정의했다는 것을 알리기 위해 override 키워드 사용. 가상함수를 다음 파생 클래스에서 더이상 재정의하지 못하게 하기 위해 final 키워드 사용
		cout << "DrvClass destructor Runs" << endl;
		delete[] ptD;
	}
};
```
   
<br />
// 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - public 상속   
`Drvd1.h` : Example of determining the scope of availability based on permission settings during Class inheritance - public inheritance   
   
```cpp
#pragma once
#include <iostream>
#include "BaseC.h"
using namespace std;

class Drvd1 : public BaseC {		// 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - public 상속
public:
	int sum() const {
		return geta() + b + c;
	}
	void printbc() const {
		cout << b << ' ' << c;
	}
};
```
   
<br />
// 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - protected 상속   
`Drvd2.h` : Example of determining the scope of availability based on permission settings during Class inheritance - protected inheritance   
   
```cpp
#pragma once
#include <iostream>
#include "BaseC.h"
using namespace std;

class Drvd2 : protected BaseC {		// 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - protected 상속
public:
	int sum() const {
		return geta() + b + c;
	}
	void printbc() const {
		cout << b << ' ' << c;
	}
};
```
   
<br />
// 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - private 상속   
`Drvd3.h` : Example of determining the scope of availability based on permission settings during Class inheritance - private inheritance   
   
```cpp
#pragma once
#include <iostream>
#include "BaseC.h"
using namespace std;

class Drvd3 : private BaseC {		// 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - private 상속
public:
	int sum() const {
		return geta() + b + c;
	}
	void printbc() const {
		cout << b << ' ' << c;
	}
};
```
   
<br />
// 추상 클래스 - 도형을 그릴 수 있는 클래스에 대한 추상 클래스   
`Figure.h` : Abstract Class - Abstract Class for Class that can draw shapes   
   
```cpp
#pragma once
#include <string>
#include "GrAttrib.h"
using namespace std;

class Figure {		// 추상 클래스 - 도형 클래스
protected:		// 파생 클래스에서는 proteted 멤버를 직접 엑세스하여 자유롭게 사용할 수 있음
	GrAttrib attrib;				// 그래픽 속성
public:
	Figure(): attrib(curAttrib) {}			// 현재 그래픽 속성에 따라 도형 객체 생성
	void setLineColor(const string& c) {		// 선 색상 속성 지정
		attrib.setLineColor(c);
	}
	void setFillColor(const string& c) {		// 내부 영역 색상 속성 지정
		attrib.setFillColor(c);
	}
	virtual void move(double dx, double dy) = 0;	// 순수가상함수 - 도형의 이동
	virtual void scale(double s) = 0;		// 순수가상함수 - 원점 기준 크기조정
	virtual void draw() const = 0;		// 순수가상함수 - 그리기 멤버함수
};
```
   
<br />
// 추상 클래스 - 도형의 그래픽 속성을 지정할 수 있는 클래스에 대한 추상 클래스   
`GrAttrib.h` : Abstract Class - Abstract Class for Class that specify graphic properties of a shapes   
   
```cpp
#pragma once
#include <string>
using namespace std;

class GrAttrib {			// 추상 클래스 - 도형의 그래픽 속성 클래스
	string lineColor;		// 선 색 속성
	string fillColor;		// 내부 영역 색 속성
public:
	GrAttrib() : lineColor("Black"), fillColor("White") {}		// 그래픽 속성 객체 생성자 - 디폴트 생성자
	GrAttrib(const string& lc, const string& fc) : lineColor(lc), fillColor(fc) {}		// 그래픽 속성 객체 생성자 - 지정된 색상으로 초기화하는 생성자
	void setLineColor(const string& lc) {		// 속성 지정 멤버함수 - 선 색상 지정
		lineColor = lc;
	}
	void setFillColor(const string& fc) {		// 속성 지정 멤버함수 - 내부 영역 색상 지정
		fillColor = fc;
	}
	string getLineColor() const {			// 속성 값을 읽는 멤버함수 - 선 색상 읽음
		return lineColor;
	}
	string getFillColor() const {			// 속성 값을 읽는 멤버함수 - 내부 영역 색상 읽음
		return fillColor;
	}
};

extern GrAttrib curAttrib;		// 전역변수 선언임. 실제 정의는 다른 파일 어딘가에 있어야 함. 현재 속성을 나타내는 전역 객체이므로 소스파일 내에서 어디서든 사용 가능. extern은 전역 객체임을 알리는 키워드임. 현재 속성을 프로그램이 끝날때까지 사용할 수 있고, 중간에 값을 변경할 수도 있음
```
   
<br />
// 함수객체를 포함한 클래스 - 함수처럼 사용될 수 있는 객체   
`Greater.h` : Class with function objects - Object that can be used as function   
   
```cpp
#pragma once

template<typename T>
class GREATER {		// 함수객체를 포함한 클래스: 함수처럼 사용될 수 있는 객체 - 함수객체처럼 사용하기 위해서는 클래스에 () 연산자가 다중정의되어 있어야 함
public:
	bool operator () (const T& a, const T& b) const {		// 함수를 호출하는 () 연산자를 다중정의 - 인라인 inline 함수임. 일반적인 인라인 함수는 함수 포인터를 만들 수 없으나 함수객체 형태로 전달하면 객체의 멤버함수인 인라인 함수를 호출하는 것처럼 만들어줌. 인라인 함수를 호출하면 일반함수를 호출하는 것에 비해 호출 절차가 매우 간단함
	return a > b;		// 내림차순
	}
};
```
   
<br >
// 사용자 정의 객체 오류 처리 예제 - 오류가 발생한 첨자 리턴   
`IntArray1.h` : Example of error handling of a custom object - Returns a subscript with an error   
   
```cpp
#pragma once
#include <ostream>
using namespace std;

const int DefaultSize = 10;
class IntArray1 {		// 사용자 정의 객체 오류 처리 예제 - 오류가 발생한 첨자 리턴
	int* buf;
	int size;
public:
	IntArray1(int s = DefaultSize);				// 생성자
	virtual ~IntArray1() { delete[] buf; }		// 소멸자 - 가상
	int& operator [] (int offset);			// 첨자 연산자 - 첨자가 범위내에 있는지 확인
	const int& operator [] (int offset) const;		// 첨자 연산자 - 첨자가 범위내에 있는지 확인
	int getSize() const { return size; }
	friend ostream& operator << (ostream&, IntArray1&);
	class BadIndex1 {		// exception class
	public:
		int wrongIndex;
		BadIndex1(int n) : wrongIndex(n) {}
	};
};
```
   
<br />
// 사용자 정의 객체 오류 처리 예제 - exception() 사용   
`IntArray2.h` : Example of error handling of a custom object - Use exception()   
   
```cpp
#pragma once
#include <ostream>
#include <exception>
using namespace std;

const int DefaultSize = 10;
class IntArray2 {		// 사용자 정의 객체 오류 처리 예제 - exception() 사용
	int* buf;
	int size;
public:
	IntArray2(int s = DefaultSize);				// 생성자
	virtual ~IntArray2() { delete[] buf; }		// 소멸자 - 가상
	int& operator [] (int offset);			// 첨자 연산자 - 첨자가 범위내에 있는지 확인
	const int& operator [] (int offset) const;		// 첨자 연산자 - 첨자가 범위내에 있는지 확인
	int getSize() const { return size; }
	friend ostream& operator << (ostream&, IntArray2&);
	class BadIndex2 : public exception {			// exception 클래스의 파생클래스오 BadIndex2 class를 만듦
	public:
		int wrongIndex;
		BadIndex2(int n) : wrongIndex(n), exception() {}
		const char* what() const {			// what은 exception의 멤버함수임. 재정의함 
			return "Array Exception::";
		}
	};
};
```
   
<br />
// 전위 표기 ++ 연산자 다중정의   
`IntClass1.h` : Prefix ++ operator multiple definitions   
   
```cpp
#pragma once

class IntClass1 {
	int a;
public:
	IntClass1(int n = 0) : a(n) {}		// 생성자
	IntClass1& operator ++ () {		// 전위 표기 ++ 연산자 다중정의
		cout << "prefix ++ operator multiple definitions : ";
		++a;
		return *this;
	}
	int getValue() const { return a; }
};
```
   
<br />
// 후위 표기 ++ 연산자 다중정의   
`IntClass2.h` : Postfix ++ operator multiple definitions   
   
```cpp
#pragma once

class IntClass2 {
	int a;
public:
	IntClass2(int n = 0) : a(n) {}		// 생성자
	IntClass2 operator ++ (int) {		// 후위 표기 ++ 연산자 다중정의
		cout << "postfix ++ operator multiple definitions : ";
		IntClass2 tmp(*this);
		++a;
		return tmp;
	}
	int getValue() const { return a; }
};
```
   
<br />
// 두 값을 비교하여 첫번째 값이 두번째 값보다 작은 경우 true를 리턴하는 템플릿 클래스 - 오름차순 정렬 함수 구현 시 사용 가능   
`Less.h` : Template Class that compares two values and returns true if the first value is less than the second value - Available when implementing an ascending sort function   
   
```cpp
#pragma once

template<typename T>
class LESS_T {		// 두 값을 비교하여 첫번째 값이 두번째 값보다 작은 경우 true를 리턴하는 템플릿 클래스 - 오름차순 정렬 함수 구현 시 사용 가능
public:
	bool operator () (const T& a, const T& b) const {
		return a < b;		// 오름차순
	}
};
```
   
<br />
// 클래스 다중상속을 위한 클래스   
`MIEmployee.h` : Class for Multiple Inheritance   
   
```cpp
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Employee1 {
	string company;
public:
	Employee1(const string& c) : company(c) {}		// 생성자
	void printCompany() const {
		cout << "printCompany() company : " << company << endl;
	}
	void print() const {
		cout << "print() company : " << company << endl;
	}
};
```
   
<br />
// 클래스를 다중상속 받는 클래스 - MIEmployee.h 와 MIStudent.h 파일의 클래스를 다중상속   
`MIParttime.h` : Class that receive multiple inheritances - Multiple inheritance of Class in the MIEployee.h and MISstudent.h files   
   
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
   
<br />
// 클래스 다중상속을 위한 클래스   
`MIStudent.h` : Class for Multiple Inheritance   
   
```cpp
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Student4 {
	string school;
public:
	Student4(const string& s) : school(s) {}		// 생성자
	void printSchool() const {
		cout << "printSchool() school : " << school << endl;
	}
	void print() const {
		cout << "print() school : " << school << endl;
	}
};
```
   
<br />
// 문자열을 정수처럼 계산할 수 있도록 연산자를 다중정의하는 예제   
`MyString.h` : Example of multiple definitions of an operator so that a string can be computed like an integer   
   
```cpp
#pragma once
#include <ostream>

class MyString {					// 문자열을 정수처럼 계산할 수 있도록 연산자를 다중정의하는 예제
	int		len;				// 문자열의 길이를 저장
	int		bufSize;			// 최대로 저장할 수 있는 문자열의 길이를 저장
	char*	buf;					// 문자열 저장 공간
	MyString(int s) : len(s), bufSize(s) {	// 생성자 (내부용으로만 사용하는 private 함수) - 저장공간 메모리 할당만 함
		buf = new char[s + 1];
		buf[s] = '\0';
	}
public:
	MyString() : len(0), bufSize(0){	// 디폴트 생성자
		buf = new char[1];		// 문자열이 없으므로 사이즈가 0이지만 null 캐릭터를 저장하기 위해 저장공간을 1 할당받아서 null 캐릭터를 저장함
		buf[0] = '\0';
	}
	MyString(const char* str) {		// 일반적인 생성자 - C스타일의 문자 자료형의 포인트 - 묵시적 형변환 가능
		len = bufSize = strlen(str);	// 문자열 길이
		buf = new char[len + 1];	// 문자열 길이만큼 저장공간 할당 - null 캐릭터가 들어갈 1 만큼의 저장공간 더해서 할당
		strcpy(buf, str);		// 문자열 복사
	}
	// explicit MyString(const char* str) {}	// 이런식으로 맨 앞에 explicit를 넣으면 묵시적인 형변환을 금지할 수 있음. 이 경우 형변환을 하려면 반드시 명시적으로 구현해야 함 e.g. str = MyString{ "Programming" }; str = static cast<MyString>("Programming");
	MyString(const MyString& mstr) : len(mstr.len), bufSize(mstr.len) {	// 복사 생성자 - 딮 카피 deep copy
		buf = new char[len + 1];
		strcpy(buf, mstr.buf);
	}
	MyString(MyString&& mstr) noexcept : len(mstr.len), bufSize(mstr.bufSize), buf(mstr.buf) {	// 이동 생성자
		mstr.buf = nullptr;
	}
	~MyString() {			// 소멸자
		delete[] buf;
	}
	int length() const {		// 문자열의 길이를 반환하는 메소드
		return len;
	}
	MyString& operator = (const MyString& mstr) {		// 대입 연산자 다중정의 - strcpy 대신 사용할 수 있게 '=' 대입 연산자를 만듦
		if (bufSize < mstr.len) {			// 문자열 공간이 필요량보다 작으면
			delete[] buf;				// 기존 공간 반환
			len = bufSize = mstr.len;		// 새로운 문자열의 길이
			buf = new char[len + 1];		// 새로운 공간 할당
		}
		else				// 그렇지 않으면
			len = mstr.len;		// 문자열의 길이만 수정
		strcpy(buf, mstr.buf);
		return *this;
	}
	MyString& operator = (MyString&& mstr) noexcept {	// 이동 연산자 다중정의
		delete[] buf;
		len = mstr.len;
		bufSize = mstr.bufSize;
		buf = mstr.buf;			// 포인터만 복사해서 메모리가 이동된 것으로 처리
		mstr.buf = nullptr;		// 메모리를 반드시 nullptr로 만들어야 함. nullptr을 하지 않을 경우 소멸자에서 delete 실행시 문제가 발생함
		return *this;
	}
	MyString operator + (const MyString& mstr) const {	// 문자열 연결 연산자 '+' 다중정의 - 두 문자열을 새로운 문자열로 합함
		MyString tmstr(len + mstr.len);			// private으로 정의한 생성자 - 메모리만 확보
		strcpy(tmstr.buf, buf);				// 앞쪽에 첫번째 문자열 복사해 넣음
		strcpy(tmstr.buf + len, mstr.buf);		// 뒤쪽에 두번째 문자열 복사해 넣음
		return tmstr;
	}
	MyString& operator += (const MyString& mstr) {	// 문자열 연결 연산자 '+=' 다중정의 - 첫번째 문자열 자기자신에 피연산자인 두번째 문자열을 붙임
		if (bufSize < len + mstr.len) {			// 메모리가 부족하면 메모리를 새로 받음
			char* tbuf = new char[(bufSize = len + mstr.len) + 1];
			strcpy(tbuf, buf);			// 자기자신의 문자열을 새로운 메모리로 복사
			delete[] buf;				// 기존 메모리 반납
			buf = tbuf;				// 새로운 메모리의 주소를 기존 buf에 넣어주어 buf가 새로운 메모리 공간을 가르키도록 함
		}
		strcpy(buf + len, mstr.buf);	// 뒤쪽에 두번째 문자열 복사해 넣음
		len += mstr.len;		// 문자열의 길이에 두번째 문자열 길이를 추가
		return *this;
	}
	bool operator == (const MyString& mstr) const {		// == 관계 연산자 다중정의
		// Todo 구현 필요
	}
	bool operator > (const MyString& mstr) const {		// > 관계 연산자 다중정의
		// Todo 구현 필요
	}
	bool operator < (const MyString& mstr) const {		// < 관계 연산자 다중정의
		// Todo 구현 필요
	}
	char& operator [] (int i) {			// 배열 값을 변경할 수 있는 첨자 연산자 다중정의
		// Todo 구현 필요
	}
	char operator [] (int i) const {		// 배열 값을 읽기만 할 수 있는 첨자 연산자 다중정의
		// Todo 구현 필요
	}
	operator char* () const {			// MyString 클래스의 객체를 C스타일 문자열로 변환 - 송신 측 클래스에서 형변환 연산자 정의
		char* pt = new char[length() + 1];	// 메모리 할당 - 문자열 길이 + 1
		strcpy(pt, buf);
		return pt;
	}
	friend std::ostream& operator << (std::ostream& os, const MyString& mstr);		// 스트림 출력 연산자 다중정의 원형 prototype - 좌측 피연산자인 cout이 ostream 클래스의 객체이기 때문에 이 MyString 클래스에서는 정의할 수 없으므로 클래스 외부에 별도로 정의함. 외부에서 클래스 내부의 멤버를 사용할 수 있게 하기 위해 friend로 설정
};

// 스트림 출력 연산자
inline std::ostream& operator << (std::ostream& os, const MyString& mstr) {		// 인라인 inline 함수는 호출 시 일반적인 호출 절차가 아니라 호출하는 위치에 함수가 그대로 들어가게 됨. inline 함수는 번역할 때 소스코드가 필요하므로 헤더 파일에 넣음. inline이 아닌 경우 별도의 cpp 파일에 넣어야 함
	os << mstr.buf;
	return os;
}
```
   
<br />
// 생성자, 소멸자 동작 예제   
`NamedObj.h` : Example of how Constructor and Destructor work   
   
```cpp
#pragma once NAMEDOBJ_H_INCLOUDED
#include <iostream>
using namespace std;

class NamedObj {		// 생성자, 소멸자 동작 예제
	char* name;
	int id;
	static int nConstr;
	static int nDestr;
public:
	NamedObj(const char* s);
	~NamedObj();
	void display() const {
		cout << "ID : " << id << " --> name : " << name << endl;
	}
	static int nObj() {
		return nConstr - nDestr;
	}
};
```
   
<br />
// noexcept 선언 예제 - 예외를 일으키지 않는다는 선언   
`noExceptT.h` : Example of a noexcept declaration - a declaration not to cause exceptions   
   
```cpp
#pragma once
#include "StackT.h"

template <typename T>
T max(const Stack<T>& v) noexcept {	// noexcept는 이 함수가 예외를 일으키지 않는다는 선언 - 이 함수를 호출하여 사용하는 곳에서도 예외 처리를 할 필요가 없음
	auto p = v.begin();
	T m = *p++;
	for (; p != v.end(); p++)
		if (m < *p) m = *p;
	return m;
};
```
   
<br />
// ++연산자 전위 표기, 후위 표기 예제 - 연필 묶음과 낱개의 개수 계산   
`Pencils.h` : Example of prefix and postfix for ++ operator - Calculate the number of pencil bundles and individuals   
   
```cpp
#pragma once

class Pencils {		// ++연산자 전위 표기, 후위 표기 예제 - 연필 묶음과 낱개의 개수 계산
	int dozens;		// 타
	int np;			// 낱개
public:
	Pencils() : dozens(0), np(0) {};	// 생성자
	Pencils(int n) {			// 생성자
		dozens = n / 12;		// 몫 구하기
		np = n % 12;			// 나머지 구하기
	}
	Pencils(int d, int n) : dozens(d), np(n) {}	// 생성자
	Pencils& operator ++ ();			// ++ 연산자 (전위 표기)
	Pencils operator ++ (int);			// ++ 연산자 (후위 표기)
	void display() const;
};
```
   
<br />
// 메모리 동적 할당 예제 - 이름과 주소를 가진 객체 생성자에 동적 할당 적용   
`Person.h` : Example of dynamically allocating memory - Dynamic assignment of memory to the Constructors of objects with names and addresses   
   
```cpp
#pragma once PERSON_H_INCLUDED

class Person {		// 메모리 동적 할당 예제
	char* name;
	char* addr;
public:
	Person(const char* name, const char* addr);		// 생성자의 원형 prototype
	~Person();						// 소멸자의 원형 prototype
	void print() const;					// const 이므로 변경 불가
	void chAddr(const char* newAddr);
};
```
   
<br />
// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 미포함   
`Person1.h` : Examples of Base Class and Derived Class - Base Class - Without Virtual Function   
   
```cpp
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Person1 {		// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 미포함
	string name;
public:
	void setName(const string& n) {
		name = n;
	}
	string getName() const {
		return name;
	}
	void print() const {
		cout << name;
	}
};
```
   
<br />
// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 미포함   
`Person2.h` : Examples of Base Class and Derived Class - Base Class - Without Virtual Function   
   
```cpp
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Person2 {		// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 미포함
	string name;
public:
	Person2(const string& n) {
		cout << "constructor of Person2" << endl;
		name = n;
	}
	~Person2() {
		cout << "destructor of Person2" << endl;
	}
	void setName(const string& n) {
		name = n;
	}
	string getName() const {
		return name;
	}
	void print() const {
		cout << name;
	}
};
```
   
<br />
// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 포함   
`Person3.h` : Examples of Base Class and Derived Class - Base Class - Include Virtual Function   
   
```cpp
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Person3 {		// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 포함 
	string name;
public:
	Person3(const string& n) : name(n) {

	}
	string getName() const {
		return name;
	}
	void print() const {
		cout << name;
	}
	virtual void printVirtual() const {		// 기초 클래스의 함수를 가상함수로 만듦
		cout << name;
	}
};
```
   
<br />
// 데이터 저장공간에 따른 첨자 접근 가능여부를 확인하는 예제   
`SafeIntArray.h` : Example of verifying that subscripts are accessible by data storage space   
   
```cpp
#pragma once
#include <iostream>

class SafeIntArray {		// 데이터 저장공간에 따른 첨자 접근 가능여부를 확인하는 예제
	int limit;		// 원소의 개수
	int* arr;		// 데이터 저장공간
public:
	SafeIntArray(int n) : limit(n) {	// 생성자
		arr = new int[n];		// 데이터 저장공간 할당
	}
	~SafeIntArray() {			// 소멸자
		delete[] arr;
	}
	int size() const {
		return limit;			// 저장 가능한 원소 개수 리턴
	}
	// 첨자 연산자를 다중정의 할 때는 값을 바꿀 수 있는 첨자 연산자와 값을 읽기만 하는 첨자 연산자를 모두 구현해야 함
	int& operator [] (int i) {		// 값을 바꿀 수 있는 (대입할 수 있는) 첨자 연산자 - i번 원소를 반환하는 멤버함수
		if (i < 0 || i >= limit) {
			std::cout << "Exit the program because the subscript is out of range.";
			exit(EXIT_FAILURE);
		}
		return arr[i];			// i번 원소 반환 - 참조를 전달
	}
	int operator [] (int i) const {	// 값을 읽기만 하는 첨자 연산자 - i번 원소를 반환하는 멤버함수
		if (i < 0 || i >= limit) {
			std::cout << "Exit the program because the subscript is out of range.";
			exit(EXIT_FAILURE);
		}
		return arr[i];			// i번 원소 반환 - 값을 전달
	}
};
```
   
<br />
// 버블 정렬 알고리즘 함수 템플릿   
`softFT.h` : Bubble Sort Algorithm Function Template   
   
```cpp
#pragma once
#include "SwapFunc.h"

template <typename T> void sortFT(T arr[], int size) {	// 버블 정렬 알고리즘 함수 템플릿 - T라는 매개변수로 전달되는 자료형에 대한 데이터 저장 배열을 받음. 받은 데이터 저장 배열의 자료형은 T임. 
	bool doAgain = true;					// for 최초 실행을 위해 초기값을 true로 지정
	for (int i = 1; doAgain; i++) {			// doAgain 이 true 이면 반복 실행
		doAgain = false;				// doAgain값을 false로 변경하고 시작 - 두번째 for에서 true로 변경되지 않으면 첫번째 for 종료됨
		for (int j = 0; j < size - i; j++)		// size 만큼 반복 실행 - 반복 시마다 제일 마지막 값이 되는 값을 제외시킬 수 있도록 size - i 지정
			if (arr[j] > arr[j + 1])		// 두 값을 비교하여 앞의 값이 크면 swapFT 함수로 순서 변경 - 오름차순 정렬 - sortFT 함수를 사용하려는 클래스에서는 대소 비교를 할 수 있는 관계 연산자의 다중정의가 정의되어 있어야 함
				swapFT(arr[j], arr[j + 1]), doAgain = true;	// 변경된 값이 있으면 doAgain 을 true로 변경하여 첫번째 for 반복 실행되도록 함
	}
};
```
   
<br />
// 클래스 템플릿 예제 - 스택이라는 자료형을 조작할 수 있는 함수 정의   
`StackT.h` : Example of a Class template - Definition of functions that can manipulate stack data type   
   
```cpp
#pragma once

template <typename T>		// typename T 또는 class T 라고 써도 됨
class Stack {			// Stack 이라는 클래스 템플릿
	T* buf;
	int top;
	int size;
public:				// 함수의 원형 prototype 선언
	Stack(int s);		// 생성자
	virtual ~Stack();	// 소멸자
	bool full() const;
	bool empty() const;
	void push(const T& a);
	void push(T&& a);
	T&& pop();
};

// 함수의 원형 prototype 과 함수의 실제 정의를 헤더 파일에 한번에 정의해야 함. 함수의 실제 정의를 별도의 cpp 파일에 넣으면 여러번 중복 정의되므로 헤더 파일에 한번에 정의해야 함
template <typename T> Stack<T>::Stack(int s) : size(s), top(s) {	// 생성자
	buf = new T[s];
}

template <typename T> Stack<T>::~Stack() {	// 소멸자
	delete[] buf;
}

template <typename T> bool Stack<T>::full() const {
	return !top;
}

template <typename T> bool Stack<T>::empty() const {
	return top == size;
}

template <typename T> void Stack<T>::push(const T& a) {
	buf[--top] = a;
}

template <typename T> void Stack<T>::push(T&& a) {
	buf[--top] = move(a);
}

template <typename T> T&& Stack<T>::pop() {
	return move(buf[top++]);
}
```
   
<br />
// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함   
`Student1.h` : Examples of Base Class and Derived Class - Derived Class - Without Virtual Function   
   
```cpp
#pragma once
#include "Person1.h"

class Student1: public Person1 {	// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함
	string school;
public:
	void setSchool(const string& s) {
		school = s;
	}
	string getSchool() const {
		return school;
	}
	void print() const {
		Person1::print();
		cout << " goes to " << school;
	}
};
```
   
<br />
// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함 - Person2 생성자를 통해 데이터멤버 초기화   
`Student2.h` : Examples of Base Class and Derived Class - Derived Class - Without Virtual Function - Initialize data Members through the Constructor of Person2   
   
```cpp
#pragma once
#include "Person2.h"

class Student2 : public Person2 {	// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함
	string school;
public:
	Student2(const string& n, const string& s) : Person2(n) {	// Person2 생성자를 통해 name 데이터멤버를 초기화 함
		cout << "constructor of Student2" << endl;
		school = s;
	}
	~Student2() {
		cout << "destructor of Student2" << endl;
	}
	void setSchool(const string& s) {
		school = s;
	}
	string getSchool() const {
		return school;
	}
	void print() const {
		Person2::print();
		cout << " goes to " << school;
	}
};
```
   
<br />
// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 포함   
`Student3.h` : Examples of Base Class and Derived Class - Derived Class - Include Virtual Function   
   
```cpp
#pragma once
#include <iostream>
#include <string>
#include "Person3.h"
using namespace std;

class Student3 : public Person3 {	// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 포함
	string school;
public:
	Student3(const string& n, const string& s) : Person3(n), school(s) {

	}
	string getSchool() const {
		return school;
	}
	void print() const {
		Person3::print();
		cout << " goes to " << school;
	}
	void printVirtual() const override final {	// 기초 클래스의 printVirtual() 함수가 가상함수이므로 파생 클래스의 함수도 가상함수가 됨. 기초 클래스의 가상함수를 재정의했다는 것을 알리기 위해 override 키워드 사용. 가상함수를 다음 파생 클래스에서 더이상 재정의하지 못하게 하기 위해 final 키워드 사용
		Person3::printVirtual();
		cout << " goes to " << school;
	}
};
```
   
<br />
// 함수 템플릿 예제 - 값을 서로 교환하는 함수   
`SwapFunc.h` : Example of a Function Template - a function that exchanges values   
   
```cpp
#pragma once
#include <iostream>
#include <utility>
using namespace std;

template <typename ANY>		// 함수 템플릿 선언
void swapFT(ANY& a, ANY& b) {		// 값을 서로 교환하는 함수
	ANY temp = move(a);		// rvalue 참조를 사용하여 이동 - 이 함수 템플릿 매개변수를 통해 전달되는 전달자 클래스는 이동 대입 연산자가 정의되어 있어야 함
	a = move(b);
	b = move(temp);
	cout << "Run swapFT function template - exchange two values" << endl;
};
```
   
<br />
// 상세 클래스 - 삼각형을 그리는 삼각형 클래스 예제   
`Triangle.h` : Detail Class - Example of a Triangle Class drawing a Triangle   
   
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
   
<br />
// Person5 클래스를 가상 기초 클래스로 상속받는 클래스 Employee2   
`VBEmployee.h` : Employee2 Class inherits Person5 Class as a Virtual Base Class   
   
```cpp
#pragma once
#include <iostream>
#include <string>
#include "VBPerson.h"
using namespace std;

class Employee2 : virtual public Person5 {	// Person5를 가상 기초 클래스로 상속받는 클래스
	string company;
public :
	Employee2(const string& n, const string& c) : Person5(n), company(c) {}
	void print() const {
		Person5::print();
		cout << "print() function in Employee2" << " is emplayed by " << company << endl;
	}
};
```
   
<br />
// Student5와 Employee2를 상속받는 클래스 - Parttime2 클래스   
`VBParttime.h` : Class that inherit Student5 Class and Employee2 Class - Parttime2 Class   
   
```cpp
#pragma once
#include "VBStudent.h"
#include "VBEmployee.h"

using namespace std;
class Parttime2 : public Student5, public Employee2 {	// Student5와 Employee2를 상속받는 클래스. Person5는 가상 기초 클래스로 상속 받았으므로 이 Parttime2 객체 내에 Person5는 1개만 상속되어 존재함
public:
	Parttime2(const string& n, const string& s, const string& c) : Person5(n), Student5(n, s), Employee2(n, c) {}	// 다중상속을 받았을 때는 Person5의 생성자를 명시적으로 호출하여 가상 기초 클래스를 초기화 해야 함
	void print() const {
		cout << "print() function in Parttime2 : " << endl;
		Student5::print();
		Employee2::print();
	}
};
```
   
<br />
// 가상 기초 클래스 - Person5 클래스   
`VBPerson.h` : Virtual Base Class - Person5 Class   
   
```cpp
#pragma once
#include <iostream>
#include <string>
using namespace std;

class Person5 {			// 가상 기초 클래스
	string name;
public:
	Person5(const string& n) : name(n) {}
	virtual ~Person5() {}		// 가상함수 소멸자
	virtual void print() const {	// 가상함수
		cout << "print() function in Person5 : " << name;
	}
};
```
   
<br />
// Person5 클래스를 가상 기초 클래스로 상속받는 클래스 Student5   
`VBStudent.h` : Student5 Class inherits Person5 Class as a Virtual Base Class   
   
```cpp
#pragma once
#include <iostream>
#include <string>
#include "VBPerson.h"
using namespace std;

class Student5 : virtual public Person5 {	// Person5를 가상 기초 클래스로 상속받는 클래스
	string school;
public:
	Student5(const string& n, const string& s) : Person5(n), school(s) {}
	void print() const {
		Person5::print();
		cout << "print() function in Student5 " << " goes to " << school << endl;
	}
};
```
   
<br />
// 다중정의에 대한 개념 이해를 위한 예제   
`VecF.h` : Example for conceptual understanding of multiple definitions   
   
```cpp
#pragma once VECF_H_INCLOUDED
#include <iostream>
#include <cstring>
using namespace std;

class VecF {		// 다중정의에 대한 개념 이해를 위한 예제
	int n;
	float* arr;
public:
	VecF(int d, const float* a = nullptr) : n{ d } {
		arr = new float[d];
		if (a) memcpy(arr, a, sizeof(float) * n);	// memcpy는 메모리의 값을 다른 메모리로 복사해줌. 매개변수로 받은 메모리값을 복사함.
	}
	VecF(const VecF& fv) : n{ fv.n} {			// 깊은 복사를 위한 명시적 복사 생성자 - 이걸 만들지 않을 경우 소멸자 ~VecF 실행시 소멸할 메모리주소가 없으므로 오류가 발생함
		arr = new float[n];
		memcpy(arr, fv.arr, sizeof(float) * n);
	}
	VecF(VecF&& fv) noexcept : n{ fv.n }, arr{ fv.arr } {	// 명시적 이동 생성자 - 초기화로 값을 옮겨줌
		fv.arr = nullptr;				// 남은값은 반드시 nullprt로 바꿔줘야 함. 소멸자 실행히 nullptr은 메모리소멸을 실행하지 않으므로 오류가 나지 않음
		fv.n = 0;
	}
	~VecF() {
		delete[] arr;
	}
	VecF add(const VecF& fv) const {
		VecF tmp(n);					// n개의 VecF를 저장할 수 있는 임시객체
		for (int i = 0; i < n; i++)
			tmp.arr[i] = arr[i] + fv.arr[i];	// 같은 자리의 값을 각각 더해줌
		return tmp;
	}
	void print() const {
		cout << "[ ";
		for (int i = 0; i < n; i++)
			cout << arr[i] << " ";
		cout << "]" << endl;
	}
	VecF& operator = (const VecF& fv) {			// 대입 연산자 다중정의 - 얕은 복사를 방지하기 위한 대입 연산자 다중정의
		cout << "Multiple definition of substitution operator : ";
		if (n != fv.n) {				// 벡터의 크기가 다르다면
			delete[] arr;				// 기존 메모리를 반환하고
			arr = new float[n = fv.n];		// 새로 메모리를 할당함
		}
		memcpy(arr, fv.arr, sizeof(float) * n);	// 데이터 복사
		return *this;
	}
	VecF& operator = (VecF&& fv) noexcept {		// 이동 대입 연산자 다중정의. rvalue 참조
		cout << "Multiple definitions of move substitution operators : ";
		delete[] arr;		// 기존 메모리를 반환하고
		n = fv.n;		// 우측 피연산자의 내용을 이동함
		arr = fv.arr;
		fv.arr = nullptr;
		return *this;
	}
};
void swapVecF1(VecF& v1, VecF& v2) {		// lvalue 참조 복사
	VecF tmp(v1);				// 복사 생성자
	v1 = v2;				// 대입 연산자 사용
	v2 = tmp;				// 대입 연산자 사용
}
void swapVecF2(VecF& v1, VecF& v2) {		// rvalue 참조 이동
	VecF tmp = move(v1);			// 이동 생성자
	v1 = move(v2);				// 이동 대입 연산자 사용
	v2 = move(tmp);				// 이동 대입 연산자 사용
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
