---
layout: post
title:  "Java: Method Overloading"
date:   2024-05-09 09:00:00 +0900
categories: [Java]
---

### Method Overloading   
// 메소드 오버로딩   
   
// 매개변수의 개수나 매개변수의 자료형이 다르면 같은 이름의 메소드를 한 클래스에서 여러 개 정의 가능   
// - 매개변수의 개수와 자료형이 일치하면 중복 정의 불가   
// - 리턴형과 접근 제어자는 구분의 기준이 되지 못함   
// 메소드를 호출할 때 가장 가까운 매개변수 목록을 가진 메소드가 호출됨   
- Multiple methods of the same name can be defined in a class if the number of parameters or the data type of the parameters is different   
  - Number of parameters, data type matching, cannot be defined in duplicate   
  - Return type and access controller are not the criteria for distinction   
- When calling a method, the method with the closest parameter list is called   
   
- Example   
   
```java
// 클래스 정의
// class definition
class PrintStream {
    public void println() {
    }
    public void println(String x) {
    }
}

// 메소드 호출
// Call Method
System.out.println();    // no argument
System.out.println("문자열");    // argument is string
System.out.println(241);    // argument is int
System.out.println(34.5);    // argument is double

// 클래스 정의
// class definition
class Mc {
    public void add(int x, int y) {
    }
    public void add(double x, double y) {
    }
}

// 메소드 호출
// Call Method
mc.add(10, 10.5);    // 'public void add(double x, double y) {}' called
```
   
#### Example of using class and object   
// 클래스와 객체의 사용 예시   
   
```java
class Cylinder {
    private Circle c;
    private int height;

    public Cylinder(Circle a, int b) {
        c = a;
        height = b;
    }

    public double getVolume() {
        return c.getArea() * height;
    }
}

class Circle {
    double radius;

    public Circle(double a) {
        radius = a;
    }

    public double getArea() {
        return radius * radius * 3.14;
    }
}

public class Main {
    public static void main(String args[]) {
        Circle c = new Circle(3);
        Cylinder cy = new Cylinder(c, 10);
        System.out.println(cy.getVolume());
    }
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
