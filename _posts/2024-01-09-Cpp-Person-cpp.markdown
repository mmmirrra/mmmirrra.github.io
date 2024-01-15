---
layout: post
title:  "C++: Person.cpp : etc sourceFile"
date:   2024-01-09 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - etc sourceFile - Person.cpp   
   
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
