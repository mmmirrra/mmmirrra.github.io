---
layout: post
title:  "Java: Class Definition"
date:   2024-05-04 09:00:00 +0900
categories: [Java]
---

### Class Definition   
// 클래스 정의   
   
// 동종 객체를 표현하기 위한 데이터 필드(멤버 변수)와 메소드를 정의함   
// - 부모 클래스의 상속, 인터페이스의 구현, 추상 클래스, final 클래스 등을 정함   
- Defines data fields (member variables) and methods for representing homogeneous objects   
  - Set inheritance of parent class, implementation of interface, abstract class, final class, etc.   
   
#### Class Definition Grammar   
// 클래스 정의 문법   
   
```java
[접근제어자] class 클래스이름
    [extends 부모클래스이름] [implements 인터페이스이름]
    {
        <데이터필드 선언>;
        <생성자 선언>;
        <메소드 선언>;
    }
```
   
```java
[access modifier] class className
    [extends parentClassName] [implements interfaceName]
    {
        <Data field Declaration>;
        <Constructor Declaration>;
        <Method Declaration>;
    }
```
   
<br />
### Method definition   
// 메소드 정의   
   
// 헤더와 몸체로 구성됨   
// - 클래스 정의 내부에 존재함   
- Made up of headers and bodies   
  - Exists inside class definition   
   
#### Method Definition Grammar   
// 메소드 정의 문법   
   
```java
[접근제어자] 반환형 메소드이름([자료형 인자[, 자료형 인자 ...]])[throws 예외이름]
{
    <문자> ...
}
```
   
```java
[access modifier] returnType methodName([dataTypeArgument[, dataTypeArgument ...]])[throws exceptionName]
{
    <character> ...
}
```
   
- Example   
   
```java
class Circle {
    ...
    public double getArea() {
        return this.r * this.r * 3.14;
    }
}
```
   
<br />
### Class definitions and use   
// 클래스 정의와 사용   
   
// 클래스 정의에서 데이터 필드와 메소드   
// - 인스턴스 변수 (메소드) 와 클래스 변수 (메소드)   
// -- 개별 객체가 소유하는 인스턴스 변수와 인스턴스 메소드   
// -- 클래스에 속한 객체가 공유하는 클래스 변수와 클래스 메소드   
// - 객체의 상태는 데이터 필드로, 행위는 메소드로 구현됨   
// - 메소드는 저장된 데이터를 이용해 기능을 수행함   
- Data Fields and Methods in Class Definitions   
  - Instance variables (methods) and class variables (methods)   
    - Instance variables and instance methods owned by individual objects   
    - Class variables and class methods shared by objects in the class   
  - The state of the object is implemented as a data field, and the action is implemented as a method   
  - Methods uses stored data to perform functions   
   
#### When will the class be used?   
// 언제 클래스를 사용하나?   
   
// 클래스형 변수를 선언할 때 (클래스는 객체의 자료형)   
// 객체를 생성할 때   
// 상속받아 클래스를 정의할 때   
- When declaring a class type variable (class is the object's data type)   
- When creating an object   
- When defining an inheritance class   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
