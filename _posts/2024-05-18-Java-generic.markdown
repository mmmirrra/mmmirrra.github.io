---
layout: post
title:  "Java: Generic"
date:   2024-05-18 09:00:00 +0900
categories: [Java]
---

### Meaning of generic   
// 제네릭의 의미   
   
// 제네릭 클래스, 제네릭 인터페이스, 제네릭 메소드   
// - 클래스, 인터페이스, 메소드를 정의할 때 타입 매개변수 (타입 파라미터) 를 선언하고 사용할 수 있음   
// - 자바 프로그램의 재사용성을 높이고 오류를 줄이는 방법   
- generic class, generic interface, generic method   
  - Type parameters (type parameters) can be declared and used when defining classes, interfaces, and methods   
  - How to make Java programs more reusable and reduce errors   
   
#### Strengths of generics   
// 제네릭의 장점   
   
// 여러 유형에 걸쳐 동작하는 일반화된 클래스나 메소드를 정의할 수 있음   
// 자료형을 한정함으로써 컴파일 시점에 자료형 검사가 가능   
// - 실행 오류를 찾아 고치는 것은 어렵기 때문   
// 캐스트 (형 변환) 연산자의 사용이 불필요   
- Allows you to define generalized classes or methods that operate across multiple types   
- Limited data type allows data type inspection at the time of compilation   
  - Because it's hard to find and fix execution errors   
- No use of cast operator required   
   
<br />
### Using Generic   
// 제네릭 사용   
   
- Example   
   
```java
class ArrayList<E> implements List<E> {
    public boolean add(E e) { ... }
    public E get(int index) { ... }
    public E remove(int index) { ... }
}
```
   
```java
public class Main {
    public static void main(String args[]) {
        List list1 = new ArrayList();
        // object 형태의 객체가 전달됨
        // Object in the object type is passed
        list1.add("hello");
        // object 형태가 반환되어 오기 때문에 String 형으로 형 변환 필요
        // Object type is returned, so type conversion to String type is required
        String s1 = (String) list1.get(0);

        List<String> list2 = new ArrayList<String>();
        // String 형태의 객체가 전달됨
        // An object in the string type is passed
        list2.add("hello");
        // String 형으로 반환되어 오기 때문에 형 변환이 필요 없음
        // No format transformation required because it is returned in String type
        String s2 = list2.get(0);
    }
}
```
   
<br />
### Generic class   
// 제네릭 클래스   
   
// 클래스 정의에서 타입 파라미터를 선언함   
// - 클래스를 사용할 때는 타입을 명시해야 함   
// 타입 파라미터는 참조형만 가능함   
// - 필드의 자료형, 메소드 반환형, 인자의 자료형으로 사용할 수 있음   
// 컴파일 할 때 명확한 타입 검사를 수행할 수 있음   
// - 메소드 호출 시 인자의 유형이 맞는지   
// - 메소드 호출의 결과를 사용할 때 유형이 맞는지   
// 자료형 매개변수로 가지는 클래스와 인터페이스를 제네릭 타입이라고 함   
- Class definition declares type parameter   
  - Type must be specified when using a class   
- Type parameter is reference type only   
  - Available as field data type, method return type, and argument data type   
- Can perform clear type checks when compiling   
  - Is the type of argument correct when calling the method   
  - Is the type correct when using the results of method calls   
- Classes and interfaces with data type parameters are called generic types   
   
<br />
### Definition of generic class   
// 제네릭 클래스의 정의   
   
// 문법   
- Grammar   
   
```java
// 접근제어자 class 클래스이름 <T1, T2, ...> {
//     ...
// }
accessModifier class className <T1, T2, ...> {
    ...
}
```
   
// 클래스 정의에서 클래스 이름의 오른편, 각 괄호 ＜ ＞ 안에 타입 파라미터를 표시함   
// 콤마 ( , ) 로 구분하여 여러 개의 타입 파라미터를 지정할 수 있음   
// 타입 파라미터는 타입을 전달 받기 위한 것   
// 타입 파라미터의 이름은 관례적으로 E, K, V, N, T, ... 을 사용함   
// - 원소 (element) 는 E 를 사용, 맵 (map) 의 키 (key) 와 값 (value) 는 K 와 V 를 사용, 타입 (type) 은 T 를 사용   
- Class definitions display type parameters in square brackets ＜ ＞ to the right of the class name   
- Multiple type parameters can be specified, separated by a comma ( , )   
- Type parameters are for receiving a type   
- Type parameters are conventionally named E, K, V, N, T, ...   
  - The element uses E, the key and value of the map use K and V, and the type uses T   
   
<br />
### Example of a generic class   
// 제네릭 클래스의 예시   
   
// 일반 클래스와 제네릭 클래스의 비교   
- Comparison between general and generic classes   
   
```java
// 일반 클래스
// General Class
class Data {
    private Object object;

    public void set(Object object) {
        this.object = object;
    }
    public Object get() {
        return object;
    }
}

// Data 클래스의 제네릭 버전
// Generic Version of Data Classes
class Data<T> {
    private T t;

    public void set(T t) {
        this.t = t;
    }
    public T get() {
        return t;
    }
}
```
   
<br />
### The need for a generic class   
// 제네릭 클래스의 필요성   
   
// 제네릭 타입과 자료형 검사   
// - 제네릭 타입을 사용하지 않으면 컴파일 시점에서 오류를 검출하지 못함   
// 의미가 명확하면 생성자 호출 시 괄호만 사용할 수 있음   
// - 예시 : `Data<String> d = new Data2<>();`   
- Generic Type and Data Type Examination   
  - Failure to detect errors at the time of compilation if generic type is not used   
- Only parentheses are allowed when calling constructors if the meaning is clear   
  - Example : `Data<String> d = new Data2<>();`   
   
```java
public class Main{
    public static void main(String args[]) {
        Data data = new Data();
        Integer i = Integer.valueOf(20);
        // 컴파일 오류 없음
        // No compile error
        data.set(i);
        // 실행 오류
        // Run error
        String s = (String) data.get();
    }
}
```
   
```java
public class Main{
    public static void main(String args[]) {
        Data<String> data = new Data<>();
        Integer i = Integer.valueOf(20);
        // 컴파일 오류
        // compile error
        data.set(i);
        String s = data.get();
    }
}
```
   
<br />
### Generic Classes Implementing Generic Interfaces   
// 제네릭 인터페이스를 구현하는 제네릭 클래스   
   
// 2개의 타입 매개변수(K, V)를 가지는 제네릭 인터페이스   
- Generic interface with two type parameters (K, V)   
   
```java
interface Pair<K, V> {
    public K getKey();
    public V getValue();
}

class OrderedPair<K, V> implements Pari<K, V> {
    private K key;
    private V value;

    public OrderedPair(K key, V value) {
        this.key = key;
        this.value = value;
    }
    public K getKey() {
        return key;
    }
    public V getValue() {
        return value;
    }
}

public class Main {
    public static void main(String args[]) {
        Pair<String, Integer> p1;
        p1 = new OrderedPair<> ("Even", 8);
        Pair<String, String> p2;
        p2 = new OrderedPair<> ("Hello", "java");
        ...
    }
}
```
   
<br />
### General classes that inherit/implement generic types   
// 제네릭 타입을 상속 / 구현하는 일반 클래스   
   
// 제네릭 인터페이스를 구현하는 일반 클래스   
// - 클래스를 정의할 때 제네릭 인터페이스의 ＜ ＞ 안에 실제 자료형을 지정하면 됨   
- General classes implementing generic interfaces   
  - When defining a class, specify the actual data type within ＜ ＞ of the generic interface   
   
```java
class MyPair implements Pair<String, Integer> {
    private String key;
    private Integer value;
    public MyPair(String key, Integer value) {
        this.key = key;
        this.value= value;
    }
    public String getKey() {
        return key;
    }
    public Integer getValue() {
        return value;
    }
}

public class Main {
    public static void main(String args[]) {
        MyPair mp = new MyPair("test", 1);
    }
}
```
   
<br />
### Raw type   
// Raw 타입   
   
// 타입 매개변수 없이 사용되는 제네릭 타입   
// - 제네릭 타입인데 일반 타입처럼 사용하는 경우   
// - 타입 매개변수를 Object로 처리함   
- Generic types used without type parameters   
  - It's a generic type, but it's used like a general type   
  - Processing Type Parameters as Objects   
   
- Example   
   
```java
class Data<T> {
    private T t;
    public Data(T t) {
        this.t = t;
    }
    public void set(T t) {
        this.t = t;
    }
    public T get() {
        return t;
    }
}
```
   
```java
// Data는 제네릭 타입 Data<T> 의 raw 타입
// 타입 매개변수를 object로 처리
// Data is generic type Data<T> raw type
// Processing Type Parameters as Objects
Data data = new Data("hello");
```
   
<br />
### Generic method   
// 제네릭 메소드   
   
// 자료형을 매개변수로 가지는 메소드   
// - 하나의 메소드 정의로 여러 유형의 데이터를 처리할 때 유용함   
// 메소드 정의에서 반환형 왼편에 각 괄호 ＜ ＞ 안에 타입 매개변수를 표시   
// - 타입 매개변수를 메소드의 반환형, 메소드 매개변수의 자료형, 지역 변수의 자료형으로 사용할 수 있음   
- Method with data types as parameters   
  - Useful for processing multiple types of data with one method definition   
- Display type parameters in square brackets ＜ ＞ to the left of the return type in the method definition   
  - Type parameters can be used as a return type of method, a data type of method parameters, and a data type of local variables   
   
```java
// 제네릭 메서드 - 배열에서 두 개의 객체를 교환
// Generic Method - Exchange two objects in an array
public <T> void swap(T[] array, int i, int j) {
    T temp = array[i];
    array[i] = array[j];
    array[j] = temp;
}
```
   
// 인스턴스 메소드와 static 메소드 모두 제네릭 메소드로 정의 가능   
// 제네릭 메소드를 호출할 때 타입을 명시하지 않아도 됨   
// - 전달되는 인자에 의해 타입의 추론이 가능함   
- Both instance and static methods can be defined as generic methods   
- When calling a generic method, you do not need to specify the type   
  - The type of inference is possible by the transmitted argument   
   
```java
class Util {
    // 제네릭 스테틱 메소드
    // Generic static method
    public static <K, V> boolean compare(Pair<K, V> p1, Pair<K, V> p2) {
        return p1.getKey().equals(p2.getKey()) && p1.getValue().equals(p2.getValue());
    }
}

public class Main {
    public static void main(String args[]) {
        Pair<Integer, String> p1 = new Pair<>(1, "apple");
        Pair<Integer, String> p2 = new Pair<>(2, "pear");
        boolean same = Util.<Integer, String>compare(p1, p2);
        System.out.println(same);
    }
}
```
   
- Result   
   
```
false
```
   
<br />
### Limiting the Type of Generic   
// 제네릭의 타입 제한   
   
// 제네릭 클래스 / 제네릭 인터페이스 / 제네릭 메소드를 정의할 때 적용 가능한 자료형에 제한을 두는 것   
// `<T extends Nember>`와 같이 하면 T를 상한으로 정할 수 있음   
// - T에 주어지는 실제 자료형은 Number 의 서브 클래스 (Integer, Long, Double 등) 여야 함   
- Limiting the data types applicable when defining generic classes/generic interfaces/generic methods   
- T can be set as the upper limit if `<T extends Nember>` is used   
  - The actual data type given to T must be a subclass of Number (Integer, Long, Double, etc.)   
   
```java
class Data<T extends Number> {
    private T t;
    public Data() {}
    public Data(T t) {
        this.t = t;
    }
    public void set(T t) {
        this.t = t;
    }
    public T get() {
        return t;
    }
}

public class Main {
    public static void main(String args[]) {
        Data<Integer> data1 = new Data<>(20);
        System.out.println(data1.get());
        Data<String> data2 = new Data<>("Hello");    // error
    }
}
```
   
<br />
### Generic Type and Type Conversion   
// 제네릭 타입과 형 변환   
   
// 상속 관계가 있어야 상위 / 하위 자료형의 관계가 존재함   
// - Integer나 Double 은 Number 의 자식 클래스   
// - 그러나 Data＜Number＞ 와 Data＜Integer＞ 사이는 상속 관계가 없고, 아무 상관 없음   
- There must be an inheritance relationship to have a higher/lower data type relationship   
  - Integrer or Double is the child class of Number   
  - However, there is no inheritance relationship between Data<Number> and Data<Integer> and nothing to do with it   
   
```java
class Data<T> {
    ...
}
// Data 클래스와 상속 관계
// Data Classes and Inheritance Relationships
class FormattedData<T> extends Data<T> {
    ...
}

public class Main {
    public static void main(String args[]) {
        Data<Number> data1 = new Data<Number>();
        // Integer, Double은 Number의 하위 클래스이므로 사용 가능
        // Integrer, Double is a subclass of Number and is therefore available
        data1.set(Integer.valueOf(10));
        data1.set(Double.valueOf(10.1));

        Data<Number> data2 = new Data<Integer>();    // compile error
        // O.K. 자식 객체를 부모 유형으로 정의하는 것은 문제 없음
        // O.K. Defining child objects as parent types is no problem
        Data<Integer> data3 = new FormattedData<Integer>();
    }
}
```
   
<br />
### Precautions when using generic type   
// 제네릭 타입 사용 시 유의 사항   
   
// 기본 자료형은 타입 매개변수로 지정할 수 없음   
// - `Data<int> d = new Data<>();    // error`   
// 타입 매개변수로 객체 생성을 할 수 없음   
// - `class Data <T> { private T t1=new T(); }    // error`   
// 타입 매개변수의 타입으로 static 데이터 필드를 선언할 수 없음   
// - `class Data <T> { private static T t2; }    // error`   
// 제네릭 타입의 배열을 선언할 수 없음   
// - `Data<Integer>[] arrayOfData;    // error`   
- Default data type cannot be specified with type parameters   
  - `Data<int> d = new Data<>();    // error`   
- Unable to create object with type parameter   
  -  `class Data <T> { private T t1=new T(); }    // error`   
- Unable to declare static data field with type of type parameter   
  - `class Data <T> { private static T t2; }    // error`   
- Unable to declare array of generic type   
  - `Data<Integer>[] arrayOfData;    // error`   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
