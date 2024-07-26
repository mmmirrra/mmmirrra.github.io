---
layout: post
title:  "Java: Abstract Class and Interface"
date:   2024-05-13 09:00:00 +0900
categories: [Java]
---

## Abstract Class and Interface   
// 추상 클래스와 인터페이스   
   
<br />
### Abstract Method   
// 추상 메소드   
   
// 메소드 정의에 `abstract` 키워드를 사용함   
// 몸체의 구현이 없이 형식만 존재하는 메소드   
// - 반환형, 메소드 이름과 인자에 관한 선언만 존재함   
// - 자식 클래스에 상속될 때, 몸체의 구현이 필요함   
// - 상반된 의미의 `final` 과 함께 사용할 수 없음   
// - 추상 메소드는 추상 클래스 또는 인터페이스에서 선언되어야 함   
- Use `abstract` keyword in method definition   
- Method that exists only in form without body implementation   
  - Only declaration exists for return type, method name, and argument   
  - When inherited to a child class, the implementation of the body is required   
  - Cannot be used with conflicting meanings of `final`   
  - Abstract methods must be declared in abstract classes or interface   
   
- Example   
   
```java
abstract class Shape {
    // 모양이 정해지지 않았기 때문에 면적을 계산할 수 없음
    // Area cannot be calculated because it has not been shaped
    abstract public double getArea();
}
```
   
<br />
### Abstract Class   
// 추상 클래스   
   
// 클래스 정의에 `abstract` 키워드를 사용함   
// - 추상 메소드를 포함할 수 있음   
// - 물론 데이터 필드나 일반 메소드를 포함할 수 있음   
// - 객체 생성을 할 수 없음   
// -- 구체적이지 못한 불완전한 클래스라는 의미   
- Use 'abstract' keyword for class definition   
  - Can contain abstract methods   
  - Can include data fields or common methods, of course   
  - Unable to create object   
    - It means an incomplete class that is not specific   
   
// 오류 예시   
- Example of an error   
   
```java
// Shape이 추상 클래스라 가정
// Suppose Shape is an abstract class
Shape s = new Shape("red");    // compile error
```
   
<br />
### Use of Abstract Class   
// 추상 클래스의 사용   
   
// 의미적으로 유사한 자식 클래스를 묶고자 할 때 사용   
// - 공통으로 사용할 데이터 필드와 메소드를 추상 클래스에서 정의   
// 추상 클래스는 불완전한 클래스   
// - 기능적으로 구현하기 어려운 메소드가 존재   
// 추상 클래스는 자식 클래스로 상속되어 사용됨   
// - 자식 클래스에서 추상 메소드를 구현해야 함   
// - 그러면 자식 클래스는 객체 생성이 가능   
// - 자식 클래스가 추상 메소드를 구현하지 않으면 계속해서 자식 클래스도 추상 클래스여야 함   
// 추상 클래스는 일반 클래스와 인터페이스의 중간적 성격을 가짐   
- Used when you want to group a class of children that is semantically similar   
  - Define common data fields and methods in abstract classes   
- An abstract class is an incomplete class   
  - There are methods that are difficult to implement functionally   
- Abstract classes are inherited and used as child classes   
  - Need to implement abstract methods in child classes   
  - Then, the child class can create objects   
  - If the child class does not implement the abstract method, the child class must also continue to be an abstract class   
- Abstract classes have an intermediate nature between normal class and interface   
   
<br />
### Interface   
// 인터페이스   
   
// 100% 추상적 클래스   
// - 인터페이스의 모든 메소드가 추상 메소드 (public abstract)   
// - 인터페이스 내에서 `public abstract`을 생략하고 사용할 수 있음   
// 몸체 없이, 구현되어야 할 메소드의 형식만 정의해 둠   
// - 단, default 인스턴스 메소드와 static 메소드는 몸체를 구현함   
// -- 모든 메소드의 기본 접근 제어자는 `public`   
// - 데이터 필드는 클래스 상수만 가능 (public static final)   
// 참조형이며 직접적 객체 생성은 불가   
// 인터페이스의 이름은 보통 형용사임   
// - 예시 : `Runnable, Serializable, Comparable`   
- 100% Abstract Class   
  - Every method in the interface is an abstract method (public abstract)   
  - `public abstract` can be omitted when used within the interface   
- Define only the type of method that should be implemented without the body   
  - However, the default instance method and the static method implement the body   
    - The default access controller for all methods is `public`   
  - Data fields can only be class constants (public static final)   
- References and cannot be created directly   
- The name of the interface is usually an adjective   
  - Example : `Runnable, Serializable, Comparable`   
   
<br />
### Defining an Interface   
// 인터페이스의 정의   
   
// 문법은 클래스 정의와 유사함   
// 정의할 때 키워드 `class` 대신 `interface`를 사용   
// - `abstract`는 생략하는 것이 일반적임   
// 메소드의 접근 제어자는 기본적으로 (생략하더라도) `public abstract` 임   
// - 몸체가 없으며, 반환형, 이름, 매개변수 목록만 표시   
// default 인스턴스 메소드와 static 메소드도 가능   
// - 이 경우 몸체를 구현해야 함   
// - 기본적으로 (생략하더라도) 접근 제어자는 `public` 임   
// 데이터 필드는 항상 (생략 가능) `public static final` 임   
// - 클래스 상수만 가능함   
- Grammar is similar to class definition   
- Use `interface` instead of the keyword `class` when defining   
  - It is common to omit `abstract`   
- The access controller of the method is basically `public abstract` (even if omitted)   
  - No body, only return type, name, parameter list   
- default instance and static methods are also possible   
  - In this case, the body must be implemented   
  - By default, the access controller is `public` (even if omitted)   
- Data fields are always (can be omitted) `public static final`   
  - Class constants only   
   
<br />
### Using the Interface   
// 인터페이스의 사용   
   
// 추상 클래스와 마찬가지로 자식 클래스에 상속 (구현) 되어 사용됨   
// 의미적으로는 관련이 없으나 기능적으로 유사한 클래스들을 묶을 때 인터페이스를 사용할 수 있음   
// - 예시 : 대소 비교가 가능한 클래스 (사각형, 사람, ... 모드 크기 비교 가능)   
// 인터페이스를 상속받아 자식 인터페이스를 정의할 수 있음   
// - 인터페이스의 상속 또는 확장   
- Inherited (implemented) and used by child classes, as with abstract classes   
- Interface can be used to group classes that are not semantically relevant but functionally similar   
  - Example : Classes with large and small comparisons (squares, people, ... mode sizes comparable)   
- Allows you to inherit an interface to define a child interface   
  - Inheritance or extension of an interface   
   
```java
// 인터페이스 정의
// Interface Definition
interface Comparable<T> {
    // 다른 객체와 크기를 비교하는 메서드
    // Method to compare size with other objects
    boolean isLargerThan(T o);
}

// 인터페이스 구현
// Implementing an Interface
class Box implements Comparable<Box> {
    private int length, width, height;
    public boolean isLargerThan(Box otherBox) {
        ...
    }
}
```
   
<br />
### Inheritance of an interface   
// 인터페이스의 상속   
   
// 자식 인터페이스가 부모 인터페이스를 상속받는 경우   
// - 기존 인터페이스를 상속받아 새로운 인터페이스를 정의할 때  키워드 `extends`를 사용   
// -- `interface 자식인터페이스 extends 부모인터페이스 { ... }`   
// - 여러 부모 인터페이스를 상속받는 다중 상속도 가능   
- The child interface inherits the parent interface   
  - Use the keyword 'extends' to inherit existing interface and define new interface   
    - `interface childInterface extends parentInterface { ... }`   
  - Multiple inheritances that inherit multiple parent interface are possible   
   
```java
// 인터페이스 정의
// Interface Definition
interface SuperInterface {
    public void func1();
    public void func2();
}

// 인터페이스 상속
// Interface Inheritance
interface SubInterface extends SuperInterface {
    public void func3();
}
```
   
<br />
### Implementing an Interface   
// 인터페이스의 구현   
   
// 자식 클래스가 부모 인터페이스를 상속받는 (구현하는) 경우   
// - 자식은 부모가 나열한 기능 (추상 메소드) 을 구현해야 함   
// - 구현을 통해 클래스를 정의할 때 `implements` 를 사용   
// -- `class 자식클래스 extends 부모클래스 implements 부모인터페이스1, 부모인터페이스2 { ... }`   
- If the child class inherits (implements) the parent interface   
  - Children must implement functions listed by their parents (abstract methods)   
  - When defining a class by implementation, use `implements`   
    - `class childClass extends parentClass implements parentInterface1, parentInterface2 { ... }`   
   
```java
// 인터페이스 정의
// Interface Definition
interface Moveble {
    void add(double dx, double dy);
    void sub(double dx, double dy);
}

// 인터페이스 정의
// Interface Definition
interface Scalable {
    void mul(double s);
    void div(double s);
}

// 인터페이스 구현
// Implementing an Interface
class Point implements Movable, Scalable {
    ...
}
```
   
#### Example of Interface Implementation   
// 인터페이스의 구현 예시   
   
```java
// 인터페이스 정의
// Interface Definition
interface Figure {
    double getArea();
}

// 인터페이스 구현
// Implementing an Interface
class Triangle implements Figure {
    private double height, width;

    public Triangle(double h, double w) {
        height = h;
        width = w;
    }

    public double getArea() {
        return height * width * 0.5;
    }
}

// 인터페이스가 구현된 클래스 객체 생성
//Create a class object with an interface implemented
public class Main {
    public static void main(String args[]) {
        Triangle t = new Triangle(3.0, 4.0);
        System.out.println(t.getArea());
    }
}
```
   
<br />
### Default Method   
// 디폴트 메소드   
   
// 인터페이스에서 선언하는 메소드에 기본 구현 (몸체) 을 넣을 수 있음   
// - 자식 클래스에서 상속받을 때 디폴트 메소드를 그대로 사용할 수 있음   
// - 메소드 선언시 `default` 를 사용하고 몸체를 구현해 줌   
// 인터페이스에 새 메소드를 추가하면 이 인터페이스를 구현하고 있던 기존 코드 (구현하고 있던 클래스 정의) 를 수정해야 되는데, 이를 피하기 위해 `default` 로 선언   
// - `default` 가 아닌 단순히 추상 메소드가 추가된다면 이 인터페이스를 구현하고 있던 클래스 전부에 추가된 메소드의 구현 코드를 추가해야 함   
- Allows default implementation (body) to be put into methods declared by the interface   
  - Default methods can be used when inheriting from a child class   
  - Use `default` to implement the body when declaring the method   
- If a new method is added to the interface, the existing code (class definition that was implemented) that was implementing this interface must be modified, and to avoid this, it is declared as `default`   
  - If an abstract method is simply added instead of `default`, the implementation code of the added method should be added to the entire class that was implementing this interface   
   
```java
interface DoIt {
    void doSomething();
    int doSomethingElse(String s);
    // 아래를 새로 추가한다면?
    // if add a new code below?
    default boolean didItWork(int i, String s) {
         ...
    }
}
```
   
<br />
### Conversion of abstract classes, interface, and class   
// 추상 클래스, 인터페이스, 클래스의 형변환   
   
// 인터페이스와 클래스는 모두 사용자 정의형임   
// `extends`와 `implements`에 따라 상위 / 하위 자료형 관계가 설정됨   
// 상위 유형의 변수는 하위 객체의 참조값을 가질 수 있음   
// 상위 유형의 변수가 가리키는 객체의 실제 유형에 따라 수행되는 메소드가 결정됨 (동적 바인딩)   
// - 실행 중 메소드 호출 시, 변수의 선언 유형으로 정하지 않음   
- Both interface and classes are customized   
- Higher/lower data type relationship is established according to `extends` and `implements`   
- Higher type of variable can have reference values of lower object   
- Depending on the actual type of object the higher type of variable points to, the method performed is determined (dynamic binding)   
  - When calling a method during execution, do not specify the declaration type of the variable   
   
- Example   
   
```java
// 자동 형변환
// Automatic transformation
SuperClass sup = new SubClass();
// method() 를 SubClass에서 찾음
// Find the method() in SubClass
sup.method();
// 컴파일 할 때는 method() 가 sup의 선언 유형에 정의되어 있는지 확인함
// When compiling, make sure that method() is defined in the declaration type of sup
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
