---
layout: post
title:  "C++: etc sourceFile list : .cpp"
date:   2024-01-09 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - etc sourceFile - .cpp   
   
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
   
<br />
// 복소수 계산 예제 - 정수   
`Complex1.cpp` : example of calculating complex number - integer   
   
```cpp
#include <iostream>
#include "Complex1.h"
using namespace std;

Complex1 Complex1::mul(const Complex1& c) const {	// 복소수 곱셈
	double r = rPart * c.rPart - iPart * c.iPart;
	double i = rPart * c.iPart + iPart + c.rPart;
	return Complex1(r, i);
}

Complex1 Complex1::div(const Complex1& c) const {	// 복소수 나눗셈
	double d = c.rPart * c.rPart + c.iPart * c.iPart;
	Complex1 c1 = mul(c.conj());
	return Complex1(c1.rPart / d, c1.iPart / d);
}

void Complex1::display() const {			// 복소수 값을 출력
	cout << "(" << rPart;
	if (iPart > 0)
		cout << "+j" << iPart;
	else if (iPart < 0)
		cout << "-j" << -iPart;
	cout << ")";
}
```
   
<br />
// 복소수 계산 예제 - 실수   
`Complex2.cpp` : example of calculating complex number - real number   
   
```cpp
#include <iostream>
#include "Complex2.h"
using namespace std;

Complex2 Complex2::operator + (const Complex2& c) const {	// 복소수 덧셈 연산자 다중정의
	cout << "Addition Operator Multiple Definition : ";
	// Complex2 tmp(*this);
	// tmp.rPart += c.rPart;
	// tmp.iPart += c.iPart;
	// return tmp;
	return Complex2(rPart + c.rPart, iPart + c.iPart);
}

Complex2 Complex2::operator + (double r) const {		// 복소수 덧셈 연산자 다중정의
	cout << "Addition Operator Multiple Definition : ";
	return Complex2(rPart + r, iPart);
}

Complex2& Complex2::operator += (const Complex2& c) {		// 복소수 복합 대입 연산자 다중정의
	cout << "Multiple Definition of Complex Substitutions Operator : ";
	rPart += c.rPart;
	iPart += c.iPart;
	return *this;
}

void Complex2::display() const {			// 복소수 값을 출력
	cout << "(" << rPart;
	if (iPart > 0)
		cout << "+j" << iPart;
	else if (iPart < 0)
		cout << "-j" << -iPart;
	cout << ")";
}

// 좌측 피연산자가 실수인 경우 덧셈 연산자 다중정의. Complex2 클래스에 속하지 않는 외부 연산자로 정의해야 함
Complex2 operator + (double r, const Complex2& c) {
	cout << "Multiple addition operator definition if left operand is real number : ";
	// return Complex2(r + c.rPart, c.iPart); -> private 멤버를 사용했기 때문에 오류 발생
	return Complex2(r + c.rPart, c.iPart);		// Complex2.h 파일에서 이 함수를 friend로 지정하였기 때문에 private 멤버를 자유롭게 사용할 수 있음
	// return Complex2(r + c.real(), c.imag());	// friend로 지정되어 있지 않은 경우 public 함수를 통해 private 멤버 값을 찾아올 수 있음
}

// 출력 연산자 다중정의. Complex2 클래스에 속하지 않는 외부 연산자로 정의해야 함
ostream& operator << (ostream& os, const Complex2& c) {
	cout << "Output operator multiple definition : ";
	os << "(" << c.rPart;		// 실수부 출력
	if (c.iPart > 0)		// 허수부 출력
		os << "+j" << c.iPart;
	else if (c.iPart < 0)
		os << "-j" << -c.iPart;
	os << ")";
	return os;
}
```
   
<br />
// 헤더파일 외부에 정의하는 함수 예제   
`Counter.cpp` : example of a function defined outside of a header file   
   
```cpp
#include <iostream>
#include "Counter.h"

using namespace std;

void Counter::f() {		// 헤더 파일 외부에 함수 정의 예제
	cout << "function f(), a function created separately by Counter.h " << endl;
};
```
   
<br />
// 사용자 정의 객체 오류 처리 예제   
`IntArray1.cpp` : example of error handling of a custom object   
   
```cpp
#include "IntArray1.h"
using namespace std;

IntArray1::IntArray1(int s) : size(s) {		// 생성자
	buf = new int[s];
	memset(buf, 0, sizeof(int) * s);
}

int& IntArray1::operator [] (int offset) {		// 첨자 연산자
	if (offset < 0 || offset >= size)		// 예외조건 검사 - 정상적인 범위인지 확인
		throw BadIndex1(offset);		// 예외객체 BadIndex 객체를 생성 및 전달
	return buf[offset];
}
```
   
<br />
// 생성자, 소멸자 동작 예제   
`NamedObj.cpp` : example of how constructor and destructor work   
   
```cpp
#include <cstring>
#include "NamedObj.h"

NamedObj::NamedObj(const char* s)		// 생성자
{
	name = new char[strlen(s) + 1];
	strcpy(name, s);
	id = ++nConstr;
}

NamedObj::~NamedObj()				// 소멸자
{
	++nDestr;
	delete[] name;
}

int NamedObj::nConstr = 0;
int NamedObj::nDestr = 0;
```
   
<br />
// ++ 연산자 전위 표기, 후위 표기 예제   
`Pencils.cpp` : example of prefix and postfix for ++ operator   
   
```cpp
#include <iostream>
#include "Pencils.h"
using namespace std;

Pencils& Pencils::operator ++ () {		// ++ 연산자 (전위 표기)
	cout << "++ operator (prefix) : ";
	if (++np >= 12)			// 낱개를 1 증가시킴. 결과가 12보다 크면
		++dozens, np = 0;		// 타 수를 1 증가시키고, 낱개는 0
	return *this;				// 증가된 결과를 반환
}

Pencils Pencils::operator ++ (int) {		// ++ 연산자 (후위 표기)
	cout << "++ operator (postfix) : ";
	Pencils tmp(*this);			// 현재 객체를 보존
	if (++np >= 12)			// 낱개를 1 증가시킴. 결과가 12보다 크면
		++dozens, np = 0;		// 타 수를 1 증가시키고, 낱개는 0
	return tmp;				// 보존된 객체를 반환
}

void Pencils::display() const {
	if (dozens) {
		cout << dozens << "bundles ";
		if (np) cout << np << "individuals ";
		cout << endl;
	}
	else
		cout << np << "individuals " << endl;
}
```
   
<br />
// 메모리 동적 할당 예제   
`Person.cpp` : example of dynamically allocating memory   
   
```cpp
#include <iostream>
#include <cstring>
#include "Person.h"

using namespace std;

Person::Person(const char* name, const char* addr) {
	this->name = new char[strlen(name) + 1];	// 이름을 저장할 메모리 공간을 동적 할당 받음
	strcpy(this->name, name);			// name의 값을 this->name 의 메모리 공간에 복사해 넣음
	this->addr = new char[strlen(addr) + 1];
	strcpy(this->addr, addr);
	cout << "create Person Object (" << name << ")" << endl;
}

Person::~Person() {
	cout << "destruction of Person object (" << name << ")" << endl;
	delete[] name;
	delete[] addr;
}

void Person::print() const {
	cout << "I am " << name << " who lives in " << addr << "." << endl;
}

void Person::chAddr(const char* newAddr) {
	delete[] addr;					// 기존 공간 반납
	addr = new char[strlen(newAddr)+1];		// 새로운 동적 메모리 공간 할당
	strcpy(addr, newAddr);
}
```
