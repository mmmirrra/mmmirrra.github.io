---
layout: post
title:  "Java: Using Objects, Class"
date:   2024-05-06 09:00:00 +0900
categories: [Java]
---

## Using Class   
// 클래스의 사용   
   
<br />
### Use an existing class that is defined   
// 정의되어 있는 기존 클래스를 사용하는 경우   
   
// 상속을 위해 클래스를 사용할 때   
- When using a class for inheritance   
   
- Example   
   
```java
Class Csub extends Csuper{...}
```
   
// 클래스형 변수를 선언할 때   
- When declaring a class type variable   
   
- Example   
   
```java
Circle c;
```
   
// 객체를 생성할 때   
// - new는 메모리 공간을 할당받고, 생성자를 호출하며, 메모리 참조값을 리턴하는 연산자   
- When creating an object   
  - new is an operator that is allocated memory space, calls the constructor, and returns a memory reference value   
   
- Example   
   
```java
c = new Circle(5);
```
   
<br />
### Use created existing objects   
// 생성된 기존 객체를 사용하는 경우   
   
// 객체 변수를 사용하는 경우   
// - 객체를 메소드의 인자로 전달하는 경우   
// - 부모 유형 변수에 객체를 대입하는 경우   
// - 이 외 사용하는 경우가 있음   
- Cases that use object variables   
  - Forwarding an object as a method argument   
  - Substituting objects in parent type variables   
  - etc.   
   
- Example   
   
```java
System.out.priintln(c);    // Forward object c
```
   
```java
Shape myShape = c;    // Substitute object c
```
   
// 객체 변수와 점 (.) 연산자를 사용하여 멤버에 접근하는 경우   
// - 객체가 소유하는 데이터 (인스턴스 변수) 를 읽거나 쓰기   
// - 객체를 이용하여 메소드 (인스턴스 메소드) 를 호출하기   
- Accessing members using object variables and point (.) operators   
  - Read or write data (instance variables) that the object owns   
  - Calls a method (instance method) using an object   
   
- Example   
   
```java
c.r = 5;    // Change the r of c
```
   
```java
c.getArea();    // Ask c to run getArea()
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
