---
layout: post
title:  "C++: StackT.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - StackT.h   
// 클래스 템플릿 예제 - 스택이라는 자료형을 조작할 수 있는 함수 정의   
`StackT.h` : example of a class template - definition of functions that can manipulate stack data type   
   
```cpp
#pragma once

template <typename T>		// typename T 또는 class T 라고 써도 됨
class Stack {			// Stack 이라는 클래스 템플릿
	T* buf;
	int top;
	int size;
public:				// 함수의 원형 선언
	Stack(int s);		// 생성자
	virtual ~Stack();	// 소멸자
	bool full() const;
	bool empty() const;
	void push(const T& a);
	void push(T&& a);
	T&& pop();
};

// 함수의 원형과 함수의 실제 정의를 헤더 파일에 한번에 정의해야 함. 함수의 실제 정의를 별도의 cpp 파일에 넣으면 여러번 중복 정의되므로 헤더 파일에 한번에 정의해야 함
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
