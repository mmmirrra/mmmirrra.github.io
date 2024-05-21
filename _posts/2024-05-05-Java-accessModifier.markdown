---
layout: post
title:  "Java: Access Modifier for Class"
date:   2024-05-05 09:00:00 +0900
categories: [Java]
---

### Access Modifier for Class   
// 클래스의 접근 제어자   
   
// 클래스의 사용 범위를 제한하는 것   
// - 생략, public, private, protected   
// - `private`과 `protected`는 내부 클래스에서만 사용함   
// `abstract`와 `final`은 사용 범위를 제한하는 접근 제어자는 아님 (비접근 제어자)   
- Limiting the scope of use of a class   
  - omit, public, private, protected   
  - `Private` and `protected` are only used in internal class   
- `abstract` and `final` are not access modifiers that limit the scope of use (non-access modifier)   
   
<br />
### Difference between omitted and public class   
// 생략된 경우와 public 클래스의 차이   
   
// 클래스 선언에서 접근 제어자가 생략된 `class`   
// - 같은 패키지에 있는 다른 클래스에서 사용 가능 (패키지 접근 수준)   
// `public class`로 선언된 경우   
// - 모든 클래스에서 즉, 어디서나 사용 가능   
- `class` with access modifier omitted from class declaration   
  - Available from different classes in the same package (package access level)   
- Declared as `public class`   
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
   
<br />
### Meaning the access modifier for data fields and methods   
// 데이터 필드, 메소드에서 접근 제어자의 의미   
   
// `private`은 같은 클래스에서만 사용 가능   
// 접근 제어자가 생략된 필드는 같은 패키지에 있는 다른 클래스에서도 사용 가능   
// `protected`는 같은 패키지와 자식 클래스에서 사용 가능   
// `public`은 모든 클래스에서 사용 가능   
- `private` is only available in the same class   
- Fields omitted by access modifier are also available in other classes in the same package   
- `protected` is available in the same package and child class   
- `public` is available in all classes   
   
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
