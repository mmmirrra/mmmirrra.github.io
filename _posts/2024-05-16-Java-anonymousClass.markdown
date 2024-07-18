---
layout: post
title:  "Java: Anonymous Class"
date:   2024-05-16 09:00:00 +0900
categories: [Java]
---

### Anonymous Class   
// 익명 클래스   
   
// 일회성으로 1개의 객체를 생성하기 위한 클래스   
// - 익명 클래스 정의와 동시에 객체를 생성할 수 있음   
// 부모 클래스를 상속받거나 인터페이스를 구현하도록 익명 클래스를 정의함   
- Classes for creating one object at a time   
  - Allows creating objects at the same time as anonymous class definitions   
- Define anonymous classes to inherit parent classes or to implement interfaces   
   
<br />
### How to define an anonymous class   
// 익명 클래스의 정의 방법   
   
// 아래에서 중괄호가 익명 클래스의 몸체가 됨   
// 부모 클래스를 상속받는 (익명 서브 클래스) 객체를 생성할 때   
// - `new 슈퍼클래스() { ... }`   
// 인터페이스를 구현하는 (익명 구현 클래스) 객체를 생성할 때   
// - `new 인터페이스() { ... }`   
- Braces become the body of an anonymous class below   
- When creating an (anonymous sub class) object that inherits the parent class   
  - `new superClass() { ... }`   
- When creating an (anonymous implementation class) object that implements an interface   
  - `new interface() { ... }`   
   
<br />
### Example object creation in anonymous sub classes   
// 익명 서브 클래스의 객체 생성 예시   
   
```java
public class Main {
    public static void main(String args[]) {
        // 익명의 자식 클래스 객체 생성
        // Create an anonymous child class object
        CSuper sub = new CSuper() {
            public int b = 20;
            public void method1() {
                System.out.println("sub1");
            }
            public void method3() {
                System.out.println("sub3");
            }
        };

        sub.method1();
        sub.method2();

        // 데이터 필드는 정적 바인딩임
        // sub의 선언 유형인 CSuper 에서 데이터 필드를 찾음
        // Data field is static binding
        // Found the data field in sub's declaration type, CSsuper
        System.out.println(sub.a);

        // sub.method3();    // compile error
        // System.out.println(sub.b);    // compile error
    }
}

class CSuper {
    public int a = 10;
    public void method1() {
        System.out.println("super1");
    }
    public void method2() {
        System.out.println("super2");
    }
}
```
   
- Result   
   
```
sub1
super2
10
```
   
<br />
### Example object creation in anonymous implementation classes   
// 익명 구현 클래스의 객체 생성 예시   
   
```java
interface MyInterface {
    public void method();
}

public class Main {
    public static void main(String args[]) {
        MyInterface sub = new MyInterface() {
            public void method() {
                System.out.println("sub1");
            }
        };
        
        sub.method();
    }
}
```
   
- Result   
   
```
sub1
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
