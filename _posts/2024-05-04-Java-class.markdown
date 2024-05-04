---
layout: post
title:  "Java: Class definitions"
date:   2024-05-04 09:00:00 +0900
categories: [Java]
---

### Class definitions   
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
### Access Modifier for Class   
// 클래스의 접근 제어자   
   
// 클래스의 사용 범위를 제한하는 것   
// - 생략, public, private, protected   
// - private과 protected는 내부 클래스에서만 사용함   
// abstract와 final은 사용 범위를 제한하는 접근 제어자는 아님 (비접근 제어자)   
- Limiting the scope of use of a class   
  - omit, public, private, protected   
  - Private and protected are only used in internal classes   
- Abstract and final are not access modifiers that limit the scope of use (non-access modifier)   
   
#### Difference between omitted and public classes   
// 생략된 경우와 public 클래스의 차이   
   
// 클래스 선언에서 접근 제어자가 생략된 class   
// - 같은 패키지에 있는 다른 클래스에서 사용 가능 (패키지 접근 수준)   
// public class로 선언된 경우   
// - 모든 클래스에서 즉, 어디서나 사용 가능   
- class with access modifier omitted from class declaration   
  - Available from different classes in the same package (package access level)   
- Declared as public class   
  - All classes—anywhere   
   
<br />
### Access Modifier for Data Field   
// 데이터 필드의 접근 제어자   
   
// 클래스 정의에서 데이터 필드나 메소드를 정의할 때도 접근 제어자를 사용함   
// - 데이터 필드를 사용할 수 있는 범위를 제한하는 것 (정보 은닉)   
// - 메소드의 접근 제어자도 의미가 같음   
- Access modifiers are also used to define data fields or methods in class definitions   
  - Limiting the extent to which data fields can be used (information hidden)   
  - The method's access modifier has the same meaning   
   
#### Meaning the access modifier for data fields and methods   
// 데이터 필드, 메소드에서 접근 제어자의 의미   
   
// private은 같은 클래스에서만 사용 가능   
// 접근 제어자가 생략된 필드는 같은 패키지에 있는 다른 클래스에서도 사용 가능   
// protected는 같은 패키지와 자식 클래스에서 사용 가능   
// public은 모든 클래스에서 사용 가능   
- Private is only available in the same class   
- Fields omitted by access modifier are also available in other classes in the same package   
- Protected is available in the same package and child class   
- Public is available in all classes   
   
|Declare members of the Alpha class|Alpha<br />(public class)|Beta<br />(Classes in the same package as Alpha)|AlphaSub<br />(Alpha's child class in a different package than Alpha's)|Gamma<br />(Classes in a different package than Alpha)|
|:---:|:---:|:---:|:---:|:---:|
|<b>public member</b>|Available|Available|Available|Available|
|<b>protected member</b>|Available|Available|Available||
|<b>If omitted</b>|Available|Available|||
|<b>private member</b>|Available||||
   
- Example   
   
```java
package com;

class Circle {
    private double r;
    public Circle(double a) {
        r = a;
    }
    public double getArea() {
        return r * r * 3.14;
    }
    public double getRadius() {
        return r;
    }
}
```
   
```java
package com;

public class Main {
    public static void main(String args[]) {
        Circle c = new Circle(5);
        System.out.println(c.r);    // error
        System.out.println(c.getRadius());
        System.out.println(c.getArea());
    }
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
