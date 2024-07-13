---
layout: post
title:  "Java: Method Chaining"
date:   2024-05-12 09:00:00 +0900
categories: [Java]
---

### Method Chaining   
// 메소드 체이닝   
   
// 하나의 명령문에서 동일 객체에 대해 연속적으로 메소드 호출을 하는 프로그래밍 기법   
// - 메소드 체이닝에 사용되는 메소드는 현재 객체의 참조값 (this) 을 반환해야 함   
// 메소드 체이닝은 프로그램의 가독성을 향상시키고, 코딩을 단순화 함   
- A programming technique in which method calls are made continuously for the same object in a single command statement   
  - The method used for method chaining must return the reference value (this) of the current object   
- Method chaining improves program readability and simplifies coding   
   
- Example   
   
```java
p.setName("Hong").setAge(30),setAddress("Seoul");
```
   
#### Example of Method Chaining   
// 메소드 체이닝 예시   
   
// 적용 전   
- Before application   
   
```java
class People {
    String name;
    int age;
    String address;

    public String getName() {
        return name;
    }
    public void setName(String name) {
        // this 생략하면 매개변수 name에 대입하게 됨
        // If 'this' is omitted, it will be substituted into the parameter name
        this.name = name;
    }
    public String getAge() {
        return age;
    }
    public void setAge(Int age) {
        this.age = age;
    }
    public String getAddress() {
        return address;
    }
    public void setAddress(String address) {
        this.address = address;
    }
}

public class Main {
    public static void main(String args[]) {
        People p = new People();
        p.setName("Hong");
        p.setAge(30);
        p.setAddress("Seoul");
    }
}
```
   
// 적용 후   
- After application   
   
```java
class People {
    String name;
    int age;
    String address;

    public String getName() {
        return name;
    }
    public People setName(String name) {    // Specifying a return type
        // this 생략하면 매개변수 name에 대입하게 됨
        // If 'this' is omitted, it will be substituted into the parameter name
        this.name = name;
        // this로 People 반환
        // Return 'People' to 'this'
        return this;
    }
    public String getAge() {
        return age;
    }
    public People setAge(Int age) {
        this.age = age;
        return this;
    }
    public String getAddress() {
        return address;
    }
    public People setAddress(String address) {
        this.address = address;
        return this;
    }
}

public class Main {
    public static void main(String args[]) {
        People p = new People();
        p.setName("Hong").setAge(30).setAddress("Seoul");
    }
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
