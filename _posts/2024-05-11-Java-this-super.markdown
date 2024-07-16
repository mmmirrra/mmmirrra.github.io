---
layout: post
title:  "Java: this, super"
date:   2024-05-11 09:00:00 +0900
categories: [Java]
---

### this   
   
// 메소드 호출 시, 숨은 인자로 `this` 가 메소드에 전달됨   
// - `this`는 현재 객체에 대한 참조값을 가지고 있음   
// - `c1.display()` 과 `c2.display()` 의 결과가 다른 이유임   
// 인스턴스 메소드나 생성자에서 필드를 참조하거나 메소드를 호출할 때 사용 가능   
// - 생략 가능함   
// - `this.필드이름`   
// - `this.메소드이름(인자)`   
- When calling the method, `this` is delivered to the method as a hidden argument   
  - `this` has a reference value for the current object   
  - That's why the results of `c1.display()` and `c2.display()` are different   
- Available when referencing a field or calling a method in an instance method or constructor   
  - Can be omitted   
  - `this.fieldName`   
  - `this.methodName(argument)`   
   
- Example   
   
```java
class Circle {
    static double PI = 3.14;
    double radius;
    ...
    public double getArea() {
        return this.radius * this.radius * PI;
    }
    public void display() {
        System.out.println("Radius : " + this.radius + " Area : " + this.getArea());
    }
}
```
   
<br />
### super   
   
// `this`와 같으나 자료형이 부모 클래스 유형임   
// 자식 클래스의 인스턴스 메소드나 생성자에서 사용됨   
// - `this`와 마찬가지로 static 메소드에서는 사용할 수 없음   
// 부모 클래스에서 오버로딩 당한 메소드를 호출하거나, 상속되었으나 감춰진 필드에 접근할 때 필요함   
// - `super.필드이름`   
// - `super.메소드이름(인자)`   
- Same as `this`, but data type is parent class type   
- Used by instance method or constructor of child class   
  - Not available in static methods like `this`   
- Required for calling overloaded methods in parent class, or accessing inherited but hidden fields   
  - `super.fieldName`   
  - `super.methodName(argument)`   
   
```java
// Parent class
class CSuper {
    public double x = 0;

    public void f() {
        System.out.println("CSuper");
    }
}

// Child class
class CSub extends CSuper {
    public double x = 1;

    // 메소드 재정의
    // Method Overriding
    public void f() {
        System.out.println("CSub");
    }

    public void print() {
        // CSuper 의 x가 출력됨
        // CSuper's x is output
        System.out.println(super.x);
        // CSuper 의 f() 가 호출됨
        // f() of CSuper called
        super.f();
    }
}
```
   
#### Example of the use of 'this' and 'super'   
// 'this'와 'super'의 사용 예시   
   
```java
class CSuper {
    public double x;
}

class CSub extends CSuper {
    public double x;
    public CSub(double new_x) {
        this.x = new_x;
        super.x = new_x * 10;
    }
    public double getSuper() {
        return super.x;
    }
    public double getSub() {
        return this.x;
    }
}

public class Main {
    public static void main(String args[]) {
        CSub sub = new CSub(10.0);
        System.out.println(sub.x);
        System.out.println(sub.getSuper());
        System.out.println(sub.getSub());
    }
}
```
   
- Result   
   
```
10.0
100.0
10.0
```
   
<br />
### Inheritance and Constructor   
// 상속과 생성자   
   
// `this()`   
// - 클래스의 생성자 내에서 같은 클래스의 다른 생성자를 호출하는 것   
// `super()`   
// - 자식 클래스의 생성자에서 부모 클래스의 생성자를 호출하는 것   
// -- 상속받은 데이터 필드를 초기화하기 위해 사용   
// - 자식 클래스의 생성자 몸체에서 부모 클래스 생성자의 명시적 호출이 없다면, 인자가 없는 생성자인 `super()` 가 자동 호출됨   
// `this()` 와 `super()` 는 생성자 몸체의 맨 앞에 위치해야 함   
- `this()`   
  - Calling another constructor of the same class within the constructor of the class   
- `super()`   
  - Calling the constructor of the parent class from the constructor of the child class   
    - Used to initialize inherited data fields   
  - If there is no explicit call from the parent class constructor in the child class constructor body, the constructor `super()` without arguments is automatically called   
- `this()` and `super()` must be placed at the beginning of the constructor's body   
   
#### Example of using 'super' and 'super()'   
// 'super' 와 'super()' 의 사용 예시   
   
```java
class Cylinder extends Circle {
    private double height;
    static final double PI = 3.14;

    // Constructor 1
    public Cylinder() {
        super();
        height = 1.0;
    }

    // Constructor 2
    public Cylinder (double radius, double h) {
        super(radius);
        this.height = h;
    }

    public double getHeight() {
        return height;
    }

    public void setHeight(double h) {
        this.height = h;
    }

    public double getArea() {
        return 2 * PI * getRadius() * height + 2 * super.getArea();
    }

    public double getVolume() {
        return super.getArea() * height;
    }

    public String toString() {
        return "Cylinder of radius = " + getRadius() + " height = " + height;
    }
}

public class Main {
    public static void main(String args[]) {
        System.out.println(new Cylinder(3, 10).getVolume());
    }
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
