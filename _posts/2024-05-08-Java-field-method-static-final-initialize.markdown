---
layout: post
title:  "Java: Static Field, Static Method, Final Field, Final Method, Initialize Field"
date:   2024-05-08 09:00:00 +0900
categories: [Java]
---

## Keywords that can be used to define Class, Data Field, and Method   
// 클래스, 데이터 필드, 메소드를 정의할 때 붙일 수 있는 키워드   
   
<br />
### Static Field   
// 정적 필드, 클래스 변수   
   
// 클래스의 모든 객체가 공유하는 데이터   
// - 객체의 생성이 없어도 항상 사용 가능   
// - 어떤 객체도 값을 변경할 수 있음   
// 사용 방법은 `클래스이름.정적필드`   
// - `객체변수.정적필드`도 가능   
- Data shared by all objects in the class   
  - Always available without object creation   
  - Any object can change its value   
- How to use it is `className.staticField`   
  - `objectVariable.staticField` is also possible   
   
- Example : `Circle.count`   
   
```java
class Circle {
    int x, y;
    int radius;
    static int count;
}
```
   
<br />
### Static Method   
// 정적 메소드, 클래스 메소드   
   
// non-static 메소드와 달리 객체와 무관하게 호출되고 실행됨   
// - 메소드 몸체에서 `this`를 사용할 수 없음   
// - static 메소드는 static 필드를 다룸   
// 호출 방법은 `클래스이름.정적메소드()`   
// - 객체와 무관하므로 클래스 이름으로 호출 가능   
// - `객체변수.정적메소드()`도 가능   
- Called and executed independently of objects, unlike non-static methods   
  - `this` is not available on method body   
  - The static method covers the static field   
- The call method is `className.staticMethod()`   
  - Can be called by class name because it is independent of the object   
  - `objectVariable.staticMethod()` is also possible   
   
// 정적 메소드를 호출하는 예시   
- Example of calling a static method   
   
```java
// 클래스 정의
// class definition
class Math {
    public static double sqrt(double a) {
        ...
    }
}

// 정적 메소드 호출
// calling static method
Math.sqrt(2.0);
Integer.parseInt("120");
```
   
<br />
### Final Field   
// 상수 필드   
   
// 상수 데이터   
// 선언할 때 초기값을 지정해야 함   
// 자주 static과 함께 사용됨   
- Constant data   
- Initial value must be specified when declaring   
- Often used with static   
   
- Example   
   
```java
final static double PI=3.141592;
```
   
<br />
### Final Method   
// 상수 메소드   
   
// 자식 클래스로 상속은 가능하나 자식 클래스에서 재정의 (오버라이딩) 할 수 없는 메소드   
- Method that can be inherited to a child class but cannot be redefined (Overriding) by a child class   
   
<br />
## Initialize Field   
// 필드의 초기화   
   
// 객체를 생성할 때 데이터 필드에 초기값을 지정하는 것   
// - 데이터 필드는 자동으로 초기값 (0, false 또는 null) 이 주어질 수 있음   
// - 클래스 변수 (static 필드) 는 프로그램이 시작될 때 초기화 됨   
// 객체 초기화를 위해 초기화 블록을 사용할 수 있음   
// - 초기화 지정을 위한 코드로, 클래스 정의에서 메소드 바깥의 임의 위치에 들어갈 수 있음   
// - static 필드는 static 초기화 블록을 사용   
- Specifying an initial value in the data field when creating an object   
  - Data fields can be automatically given an initial value (0, false, or null)   
  - Class variables (static fields) are initialized at the start of the program   
- Initialization blocks are available for object initialization   
  - Code for initialization, which can enter any location outside the method in the class definition   
  - The static field uses a static initialization block   
   
// 필드 초기화 방법의 실행 순서   
// 1. static 필드의 선언문에서 초기화   
// 2. static 초기화 블록 실행   
// 3. non-static 필드의 선언문에서 초기화   
// 4. non-static 초기화 블록 실행   
// 5. 생성자 실행   
- Order of run of field initialization methods   
    1. Initialize from declaration in static field   
    2. Run static initialization blocks   
    3. Initialize from declaration in non-static field   
    4. Run non-static initialization blocks   
    5. Run constructors   
   
// 예시   
// - nStatic 초기값은 1, nValue 초기값은 3이 됨   
- Example   
  - nStatic initial value is 1 and nValue initial value is 3   
   
```java
class IniTest {
    static int nStatic = 0;
    int nValue = 1;

    // 인스턴스 변수 초기화
    // Initializing the instance variable
    {
        nValue = 2;
    }

    // static 필드 초기화
    // Initializing the static field
    static {
        nStatic = 1;
    }

    // 생성자 내의 초기화
    // Initialization within the constructor
    public IniText() {
        nValue = 3;
    }
}
```
   
// 예시   
// - 데이터 필드 초기화   
- Example   
  - Initialize data fields   
   
```java
import java.awt.Point;

class Rectangle {
    // data fields
    public int width = 0;
    public int height = 0;
    public Point origin;

    // constructor 1
    public Rectangle() {
        origin = new Point(0, 0);
    }

    // constructor 2
    public Rectangle(Point p, int w, int h) {
        origin = p;
        width = w;
        height = h;
    }
}

public class Main {
    public static void main(String args[]) {
        Point originOne = new Point(23, 94);
        Rectangle rectOne = new Rectangle(originOne, 100, 200);
    }
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
