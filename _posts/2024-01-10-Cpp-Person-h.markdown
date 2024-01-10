---
layout: post
title:  "C++: Person.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - Person.h   
`Person.h` : example of dynamically allocating memory - dynamic assignment of memory to the constructors of objects with names and addresses // 메모리 동적 할당 예제 - 이름과 주소를 가진 객체 생성자에 동적 할당 적용   
   
```cpp
#pragma once PERSON_H_INCLUDED

class Person {		// 메모리 동적 할당 예제
	char* name;
	char* addr;
public:
	Person(const char* name, const char* addr);		// 생성자의 원형
	~Person();						// 소멸자의 원형
	void print() const;					// const 이므로 변경 불가
	void chAddr(const char* newAddr);
};
```
