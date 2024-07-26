---
layout: post
title:  "Java: Polymorphism"
date:   2024-05-14 09:00:00 +0900
categories: [Java]
---

## Polymorphism   
// 다형성   
   
// 유사하지만 다양한 형상이나 다양한 기능을 가진다는 뜻   
// - 한 부모에서 나온 두 자식 객체는 비슷하지만 다름   
// - 하나의 클래스에서 오버로딩된 메소드들은 유사하지만 조금씩 다른 기능을 수행함   
// - 자식 클래스에서 재정의된 메소드는 부모의 것과 유사하지만 다른 기능을 수행함   
- It means that it is similar but has a variety of shapes or functions   
  - Two child objects from a single parent are similar but different   
  - Overloaded methods in one class perform similar but slightly different functions   
  - The overridden method in the child class is similar to the parent's, but performs a different function   
   
<br />
### Polymorphism and Type conversion   
// 다형성과 형 변환   
   
#### Type conversion   
// 형 변환   
   
// 상속 관계에 있는 클래스 간에는 타입 변환이 가능함   
// - 전혀 다른 두 클래스 간에는 타입 변환이 금지됨   
// 자식 (하위) 클래스에서 부모 (상위) 클래스로의 형 변환은 문제 없음   
// - 업캐스팅이라 하며 자동으로 형 변환 가능함   
// - 참조형 변수는 같은 유형 또는 자식 유형의 객체를 참조할 수 있음   
- Type conversion is possible between classes in an inheritance relationship   
  - Type conversion is prohibited between two completely different classes   
- Type conversion from child (sub) class to parent (upper) class is no problem   
  - It is called upcasting and can be automatically type conversion   
  - Reference variables can refer to objects of the same type or child type   
   
- Example   
   
```java
// 하위 객체 참조 - 자식 유형이 부모 유형으로 형 변환됨
// (Animal) 생략 가능
// Refer to Sub-Objects - Child Type conversion to Parent Type
// (Animal) Can be omitted
Animal animal = (Animal) new Dog();
```
   
#### The effect of polymorphism   
// 다형성의 활용 효과   
   
// 코드의 유연성과 재사용성   
// 동적 바인딩을 통해 실제 유형을 명시적으로 다룰 필요가 없음   
- Flexibility and Reusability of Code   
- Dynamic binding does not require explicit handling of the real type   
   
<br />
### Polymorphism and Overriding   
// 다형성과 오버라이딩   
   
// 클래스의 다형성   
// - 부모 클래스로부터 상속받은 메소드를 자식 클래스에서 오버라이딩 할 수 있음   
// - 부모와 자식에서 같은 이름의 메소드가 다른 기능을 수행   
// -- 메소드 이름, 매개변수, 반환형은 같으나 몸체의 구현이 다름   
// - 서로 다른 자식 간에도 같은 이름의 메소드가 다른 기능을 수행   
// 인터페이스의 다형성   
// - 자식 클래스들에서 상위 인터페이스의 메소드를 다르게 구현함   
- Polymorphism of Class   
  - Methods inherited from the parent class can be overridden by the child class   
  - Methods of the same name perform different functions for parents and children   
    - Method names, parameters, and return types are the same, but body implementations are different   
  - Different children perform different functions using the same name method   
- Polymorphism of the Interface   
  - Differently implemented methods of parent interface in child classes   
   
#### Example 1 of Class Inheritance and Polymorphism   
// 클래스 상속과 다형성 예시 1   
   
```java
class A {
    public void func() {
        System.out.println("A");
    }
}

class B extends A {
    public void func() {
        System.out.println("B");
    }
}

class C extends B {
    public void func() {
        System.out.println("C");
    }
}

public class Main {
    public static void main(String args[]) {
        A a = new B();
        a.func();
        a = new C();
        a.func();
    }
}
```
   
- Result   
   
```
B
C
```
   
#### Example of 2 Class Inheritance and Polymorphism   
// 클래스 상속과 다형성 예시 2   
   
```java
class Employee {
    int nSalary;
    String szDept = null;
    public void doJob() {
        System.out.println("Do something");
    }
}

class Sales extends Employee {
    public Sales() {
        szDept = "Sales Dept";
    }
    public void doJob() {
        System.out.println("Do sales");
    }
}

class Development extends Employee {
    public Development() {
        szDept = "Dev. Dept";
    }
    public void doJob() {
        System.out.println("Do development");
    }
}

public class Main {
    public static void main(String args[]) {
        Employee emp1, emp2;
        emp1 = new Sales();
        emp2 = new Development();
        emp1.doJob();
        emp2.doJob();
    }
}
```
   
- Result   
   
```
Do sales
Do development
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
