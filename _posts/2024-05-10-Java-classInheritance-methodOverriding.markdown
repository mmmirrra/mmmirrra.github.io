---
layout: post
title:  "Java: Class Inheritance, Method Overriding"
date:   2024-05-10 09:00:00 +0900
categories: [Java]
---

### Class Reuse   
// 클래스의 재사용   
   
// 합성   
// - 기존 클래스의 새로운 클래스 정의에서 데이터 필드의 자료형으로 사용   
// - "has-a" 관계   
// 상속   
// - 기존 클래스 (부모) 를 사용하여 새로운 클래스 (자식) 를 정의   
// - 코드의 중복 작성을 줄이고 프로그램의 확장성이 좋아짐   
// - 상속은 기존 클래스의 확장 or 특화하는 것   
// - 자식 "is-a" 부모의 관계   
- Synthesis   
  - Use as a data type in a data field in a new class definition of the existing class   
  - "has-a" relationship   
- Inheritance   
  - Define a new class (child) using an existing class (parent)   
  - Reduce duplication of code and increase program scalability   
  - Inheritance is an extension or specialization of an existing class   
  - The parent-child relationship of "is-a"   
   
// 합성 예시   
- Example of synthesis   
   
```java
class Line {
    Point begin, end;
    ...
}
```
   
<br />
### Class Inheritance   
// 클래스의 상속   
   
// 상속은 부모 클래스와 자식 클래스 간의 관계   
// - 자식 클래스가 부모 클래스의 필드와 메소드를 상속 받음   
// - 기존 클래스를 상속받을 때 키워드 `extends` 를 사용함   
// - 자식 클래스에서 상속받은 메소드를 재정의 (오버라이딩) 할 수 있음   
- Inheritance is the relationship between parent and child classes   
  - Child class inherits fields and methods of parent class   
  - Use the keyword `extends` when inheriting an existing class   
  - Can override (Overriding) methods inherited from child classes   
   
- Example   
   
```java
class Manager extends Employee {
    ...
}
```
   
// 클래스의 상속은 단일 상속만 가능   
// - 인터페이스 상속의 경우는 다중 상속 가능   
- Class inheritance can only be a single inheritance   
  - Multiple inheritability is possible for interface inheritance   
   
#### Example of Inheritance of a Class   
// 클래스의 상속 예시   
   
```java
class CSuper {
    private int f1;
    public int f2;

    public void setPrivate(int i) {
        f1 = i;
    }
    public void setPublic(int i) {
        f2 = i;
    }
    private void mPrivate() {
        f1 = 30;
    }
}

class CSub extends CSuper {
    private int f3;
    public int f4;
}

public class Main {
    public static void main(String args[]) {

        CSub sub = new CSub();

        sub.f1 = 40;    // error - private data field
        sub.f2 = 50;
        sub.f3 = 60;    // error - private data field
        sub.f4 = 70;
        sub.setPrivate(10);
        sub.setPublic(20);
        sub.mPrivate();    // error - private method
    }
}
```
   
<br />
### Method Overriding   
// 메소드 오버라이딩   
   
// 부모로부터 상속받은 메소드의 몸체를 자식 클래스에서 재정의하는 것   
// 부모와 자식에서 같은 이름의 메소드가 다른 기능을 수행하게 됨   
- Redefining the body of the method inherited from the parent in the child class   
- Methods of the same name perform different functions for parents and children   
   
#### How to Overriding   
// 오버라이딩 방법   
   
// 메소드의 이름, 인자의 개수와 자료형, 반환형이 같은 메소드를 정의   
// 단, 반환형은 서브 타입 (상속 관계에서 자식 클래스) 도 가능함   
// 접근 제어자의 가시성 (접근 범위) 은 같거나 커져야 함   
// - protected인 경우 → protected 또는 public 가능   
// - public인 경우 → public만 가능   
- Define a method with the same name, number of arguments, data type, and return type   
- However, the return type can also be subtype (child class in inheritance relationship)   
- Access controller visibility (access range) must be equal or greater   
  - If protected → protected or public enabled   
  - If public → only public enabled   
   
// 메소드 오버라이딩 예시   
- Example Method Overriding   
   
```java
class Shape {
    public double getArea(double h, double w) {
        return h * w;
    }
}

class Triangle extends Shape {
    // Method Overriding
    public double getArea(double h, double w) {
        return h * w * 0.5;
    }
}

public class Main {
    public static void main(String args[]) {
        Shape t = new Triangle();
        // Triangle의 메소드 호출됨
        // Method of Triangle called
        System.out.println(t.getArea(3.0, 4.0));
    }
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
