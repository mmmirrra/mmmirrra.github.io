---
layout: post
title:  "Java: Use of Objects"
date:   2024-05-04 09:00:00 +0900
categories: [Java]
---

### Using Classes   
// 클래스의 사용   
   
#### Use an existing class that is defined   
// 정의되어 있는 기존 클래스를 사용하는 경우   
   
// 상속을 위해 클래스를 사용할 때   
- When using a class for inheritance   
   
- Example   
   
```java
Class Csub extends Csuper{...}
```
   
// 클래스형 변수를 선언할 때   
- When declaring a class type variable   
   
- Example   
   
```java
Circle c;
```
   
// 객체를 생성할 때   
// - new는 메모리 공간을 할당받고, 생성자를 호출하며, 메모리 참조값을 리턴하는 연산자   
- When creating an object   
  - new is an operator that is allocated memory space, calls the constructor, and returns a memory reference value   
   
- Example   
   
```java
c = new Circle(5);
```
   
#### Use created existing objects   
// 생성된 기존 객체를 사용하는 경우   
   
// 객체 변수를 사용하는 경우   
// - 객체를 메소드의 인자로 전달하는 경우   
// - 부모 유형 변수에 객체를 대입하는 경우   
// - 이 외 사용하는 경우가 있음   
- Cases that use object variables   
  - Forwarding an object as a method argument   
  - Substituting objects in parent type variables   
  - etc.   
   
- Example   
   
```java
System.out.priintln(c);    // Forward object c
```
   
```java
Shape myShape = c;    // Substitute object c
```
   
// 객체 변수와 점 (.) 연산자를 사용하여 멤버에 접근하는 경우   
// - 객체가 소유하는 데이터 (인스턴스 변수) 를 읽거나 쓰기   
// - 객체를 이용하여 메소드 (인스턴스 메소드) 를 호출하기   
- Accessing members using object variables and point (.) operators   
  - Read or write data (instance variables) that the object owns   
  - Calls a method (instance method) using an object   
   
- Example   
   
```java
c.r = 5;    // Change the r of c
```
   
```java
c.getArea();    // Ask c to run getArea()
```
   
<br />
### Constructor   
// 생성자   
   
// 객체가 생성될 때 자동으로 실행되는 메소드   
// - 객체의 필드 값을 초기화하거나 메모리 할당 등의 작업   
- A method that runs automatically when an object is created   
  - Actions such as initializing the field value of an object or allocating memory   
   
// 객체 생성 방법은 new 클래스이름(인자 ...)   
// - new 연산자를 이용하여 객체를 생성 (메모리 할당) 하고 생성자가 호출 (데이터 필드의 초기화) 되면서 객체의 참조값을 변수에 대입 (=)   
- The object creation method is a new className(argument...)   
  - Create an object (memory allocation) using the new operator and substitute the object's reference value into the variable (=) as the constructor calls (initializes the data field)   
   
- Example   
   
```java
Circle c = new Circle(5);
```
   
// 인자가 없는 생성자를 기본 생성자 (defualt constructor) 라고 함   
- A constructor without a argument is called a default constructor   
   
#### Definition of Constructor   
// 생성자의 정의   
   
// 보통의 메소드와 정의 방법이 다름   
// - 생성자는 new를 사용하여 객체를 생성할 때 호출됨   
- Different from the usual methods and how they are defined   
  - Constructor is called when creating objects using new   
   
#### How to define a Constructor   
// 생성자 정의 방법   
   
// 생성자 이름은 클래스 이름과 같음   
// 반환형을 지정할 수 없음   
// 한 클래스에서 여러 생성자를 정의할 수 있음 (생성자 오버로딩)   
//  - 매개변수의 개수와 매개변수의 자료형으로 구분   
// 접근 제어자는 보통 public   
- The constructor name is the same as the class name   
- Cannot specify a return type   
- Multiple constructors can be defined in one class (constructor Overloading)   
  - Separated by number of parameters and data types of parameters   
- Access modifiers are usually public   
   
- Example   
   
```java
class Circle {
    double r;
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
public class Main {
    public static void main(String args[]) {
        Circle c = new Circle(5.0);
        System.out.println(c.r);
        System.out.println(c.getArea());
    }
}
```
   
#### Default Constructor   
// 기본 생성자   
   
// 인자가 없는 생성자, 디폴트 생성자 (default constructor)   
- Constructor without argument, Default constructor   
   
// 클래스 정의에서 단 하나의 생성자 정의도 없다면 컴파일러가 다음과 같은 것을 자동으로 만들어 줌   
- If there is no single constructor definition in the class definition, the compiler automatically creates the following   
   
- Example   
   
```java
public Circle() {}
```
   
// 자식 클래스에서 생성자 몸체의 첫 줄에 부모 생성자의 명시적 호출이 없다면, 자식 클래스의 생성자에는 다음 코드가 자동으로 들어감   
- If there is no explicit invocation from the parent constructor in the first line of the constructor body in the child class, the constructor in the child class automatically contains the following code   
   
```java
// 부모 클래스의 기본 생성자를 호출
// Call the defualt constructor of the parent class
super();
```
   
// 따라서 부모 클래스에서 기본 생성자의 존재를 확인해야 함   
- Therefore, it is necessary to confirm the existence of the underlying constructor in the parent class   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
