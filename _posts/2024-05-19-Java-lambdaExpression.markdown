---
layout: post
title:  "Java: Lambda Expression"
date:   2024-05-19 09:00:00 +0900
categories: [Java]
---

### Lambda Expression   
// 람다식   
   
// 인터페이스를 구현하는 익명 클래스의 객체 생성 부분을 수식화 한 것   
// - 구현할 것이 1개의 추상 메소드뿐인 경우, 간단히 표현할 수 있음   
- Formulated the object creation part of the anonymous class that implements the interface   
  - Can be easily represented if there is only one abstract method to implement   
   
```java
// 익명 구현 클래스
// Anonymous Implementation Class
Runnable runnable = new Runnable() {
    public void run() {
        ...
    }
}
```
   
#### Lambda Expression statement   
// 람다식 구문   
   
// 메소드 매개변수의 괄호, 화살표, 메소드 몸체로 표현   
// - `인터페이스 객체변수 = (매개변수목록) -> { 실행문 목록 };`   
- Represented by parentheses, arrows, and method bodies of method parameters   
  - `Interface object variable = (parameter list) -> {executive statement list };`   
   
- Example   
   
```java
Runnable runnable = () -> {
    ...
};
```
   
<br />
### Lambda Expression basic grammar   
// 람다식 기본 문법   
   
// 익명 구현 클래스의 객체 생성 부분만 람다식으로 표현함   
// - 익명 서브 클래스의 객체 생성은 람다식이 될 수 없음   
// 이때 인터페이스에는 추상 메소드가 1개만 있어야 함   
// - 2개 이상의 추상 메소드를 포함하는 인터페이스는 사용 불가   
// 람다식의 결과 타입을 타깃 타입이라고 함   
// - 타깃 타입으로부터 여러가지를 추론할 수 있음   
// 1개의 추상 메소드를 포함하는 인터페이스를 함수형 인터페이스라 함   
// - 메소드가 1개 뿐이므로 메소드 이름을 생략할 수 있음   
// - 람다식은 이름 없는 메소드 선언과 유사함   
- Only object generation parts of the anonymous implementation class are represented in a lambda expression   
  - Object creation in anonymous subclass cannot be lambda expression   
- The interface must have only one abstract method at this time   
  - Interface containing more than one abstract method are not available   
- lambda expression's result type is called the target type   
  - We can deduce a number of things from the target type   
- An interface containing one abstract method is called a functional interface   
  - There is only one method, so the method name can be omitted   
  - Lambda expression is similar to an unnamed method declaration   
   
// `인터페이스 객체변수 = (매개변수목록) -> { 실행문 목록 };`   
// - 매개변수 목록에서 자료형은 인터페이스(타깃 타입) 정의에서 알 수 있으므로 자료형을 생략하고 변수 이름만 사용 가능   
// - 매개변수가 1개면 괄호도 생략 가능하며, 이때 변수 이름 하나만 남음   
// -- 예시 : `f1 = a -> { ...; };`   
// - 매개변수를 가지지 않으면 괄호만 남음   
// -- 예시 : `f1 = () -> { ...; };`   
// - 화살표 사용   
// - 실행문 목록에서 실행문이 1개면 중괄호 생략 가능   
// -- 예시 : `Runnable runnable = () -> System.out.println("my thread");`   
// - 단, 실행문이 return 문 뿐이라면 return 과 (수식 다음의) 세미콜론, 중괄호를 동시에 생략하고 1개의 수식만 적어야 함   
// -- 예시 : `f1 = (a, b) -> { return a + b; };` → `f2 = (a, b) -> a + b;`   
- `Interface object variable = (parameter list) -> {executive statement list };`   
  - In the parameter list, data type is known from the interface (target type) definition, so you can skip data type is use only variable name   
  - If there is one parameter, parentheses can also be omitted, leaving only one variable name   
    - Example : `f1 = a -> { ...; };`   
  - If there is no parameter, only parentheses remain   
    - Example : `f1 = () -> { ...; };`   
  - Using arrows   
  - 1 execution statement in the list of execution statements can omit brackets   
    - Example : `Runnable runnable = () -> System.out.println("my thread");`   
  - However, if the execution statement is only the return statement, the return, semicolon (after the equation), and the brace must be omitted at the same time and only one equation must be written   
    - Example : `f1 = (a, b) -> { return a + b; };` → `f2 = (a, b) -> a + b;`   
   
<br />
### Example 1 of lambda expression usage   
// 람다식 사용 예시 1   
   
```java
interface Addable {
    int add(int a, int b);
}

public class Main {
    public static void main(String args[]) {

        // 익명 구현 클래스의 객체 생성 - 람다식을 사용하지 않은 경우
        // Creating Objects in Anonymous Implementation Class - If Lambda expression is not used
        Addable ad1 = new Addable() {
            public int add(int a, int b) {
                return (a + b);
            }
        };
        System.out.println(ad1.add(100, 200));

        // 매개변수 목록과 return 문을 가진 람다식 - 이 형태를 실제로 사용하지는 않음
        // Lambda expression with a list of parameters and a return statement - do not actually use this form
        Addable ad2 = (int a, int b) -> {
            return (a + b);
        };
        System.out.println(ad2.add(10, 20));

        // 간단한 람다식
        // a simple Lambda expression
        Addable ad3 = (a, b) -> (a + b);
        System.out.println(ad3.add(1, 2));

    }
}
```
   
<br />
### Example 2 of lambda expression usage   
// 람다식 사용 예시 2   
   
```java
interface MyInterface1 {
    public void method(int a, int b);
}

interface MyInterface2 {
    public void method(int a);
}

public class Main {
    public static void main(String args[]) {
        MyInterface1 f1, f2, f3;
        MyInterface2 f4, f5;

        f1 = (int a, int b) -> {
            System.out.println(a + b);
        };
        f1.method(3, 4);

        f2 = (a, b) -> {
            System.out.println(a + b);
        };
        f2.method(5, 6);

        f3 = (a, b) -> System.out.println(a + b);
        f3.method(7, 8);

        f4 = (int a) -> {
            System.out.pringln(a);
        };
        f4.method(9);

        f5 = a -> System.out.println(a);
        f5.method(10);
    }
}
```
   
- Result   
   
```
7
11
15
9
10
```
   
<br />
### The use of the lambda expression   
// 람다식의 활용   
   
// 함수형 인터페이스 (functional interface)   
// - 1개의 추상 메소드만 가지는 단순한 인터페이스를 함수형 인터페이스라 함   
// - 패키지 java.util.function 에서 표준 함수형 인터페이스가 제네릭 인터페이스로 제공됨   
// - 함수형 인터페이스를 구현하는 클래스를 정의할 때 익명 클래스 정의를 활용할 수 있으나 람다식이 효율적   
- functional interface   
  - A simple interface with only one abstract method is called a functional interface   
  - A standard functional interface is provided as a generic interface in the package java.util.function   
  - Anonymous class definitions can be used to define classes that implement functional interface, but lambda expressions are efficient   
   
#### Example of a Standard Functional Interface   
// 표준 함수형 인터페이스의 예시   
   
// `Consumer<T>` 는 `void accept(T t)`를 가짐   
// `Supplier<T>` 는 `T get()`를 가짐   
// `Function<T, R>` 은 `R apply(T t)`를 가짐   
- `Consumer<T>` has `void accept(T t)`   
- `Supplier<T>` has `T get()`   
- `Function<T, R>` has `R apply(T t)`   
   
<br />
### Functional Interface and Lambda Expression   
// 함수형 인터페이스와 람다식   
   
```java
public class Main {
    public static void main(String args[]) {
        // 람다식으로 표현하여 생성한 객체가 생성자의 인자 (매개변수) 로 전달됨
        // 객체가 생성자의 인자로 전달된 것임
        // The object created by Lambda expression is passed to the constructor's argument (parameter)
        // Object is passed by the constructor's argument
        Thread thd = new Thread(() -> System.out.println("my thread"));
        thd.start();
    }
}
```
   
- Result   
   
```
my thread
```
   
#### Example of Standard Functional Interface Supplier<T>   
// 표준 함수형 인터페이스 `Supplier<T>` - 예시   
   
```java
import java.util.function.*;

public class Main{
    public static void main(String args[]) {
        Supplier<Integer> rand = () -> {
            // Math.radom() 은 [0, 1] 사이의 임의의 실수값을 리턴해줌
            // Math.radom() returns any real number value between [0, 1]
            Integer r = (int) (Math.random() * 10);
            return r;
        };

        int a = rand.get();
        System.out.println(a);
    }
}
```
   
- Result   
   
```
// 0 ~ 9 사이의 임의의 숫자가 랜덤으로 출력됨
Any number between 0 and 9 is randomly output
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
