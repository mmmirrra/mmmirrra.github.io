---
layout: post
title:  "Java: Array, String"
date:   2024-05-04 09:00:00 +0900
categories: [Java]
---

### Array   
// 배열   
   
// 같은 자료형의 원소를 정해진 개수만큼 가지고 있는 객체   
// - 배열의 크기는 배열이 초기화 또는 생성될 때 정해짐   
// - 숫자 인덱스(첨자)를 사용하여 특정 원소를 다룸   
- An object with a fixed number of elements of the same data type   
  - The size of the array is determined when the array is initialized or created   
  - Use a numeric index (subscript) to address a particular element   
   
#### Declaration of Arrangements   
// 배열의 선언   
   
// 선언할 때 크기를 지정할 수 없음   
// 형식은 `자료형[] 변수이름;` 또는 `자료형 변수이름[];`   
- Cannot specify a size when declaring   
- The format is `dataType[] variableName;` or `dataType variableName[];`   
   
- Example   
   
```java
int[] a;
int b[];
int[][] c;
int d[][];
int[] e[];

int f[10]; // Error
```
   
#### Initialization of Array   
// 배열의 초기화   
   
// 선언과 동시에 중괄호를 이용하여 초기값을 지정   
// - 자동으로 메모리 공간이 확보됨   
// - 초기화 또는 생성 과정을 거쳐야 배열의 원소를 사용할 수 있음   
- Use brackets to specify initial values at the same time as the declaration   
  - Automatically free up memory space   
  - Elements in the array can only be used after initialization or creation   
   
- Example   
   
```java
int a[] = {2, 3, 5, 7, 11};    // Initialize upon declaration
```
   
```java
int anArray[][] = {{1, 2, 3}, {4, 5, 6}}
```
   
```java
int b[];
b = {4, 5, 6};    // Error
```
   
#### Creating an Array   
// 배열의 생성   
   
// 배열의 원소가 사용할 메모리 공간의 생성   
// - new 연산자를 이용   
// -- 배열의 크기를 정하고 메모리 공간을 확보   
// -- new 연산자는 메모리의 주소값을 리턴함   
// -- 원소가 숫자인 경우 0, 참조형인 경우 null로 자동 초기화   
- Creating memory space for the elements in the array to use   
  - Using the new operator   
    - Size the array and free up memory space   
    - The new operator returns the address value of the memory   
    - Auto-initialize elements to 0 if they are numbers or null if they are references   
   
- Example   
   
```java
int a[] = new int[3];    // Declaration and Creation
```
   
```java
int b[];
b = new int[10];
```
   
```java
int anArray4[][] = new int[3][2];
```
   
#### The size of Array   
// 배열의 크기   
   
// 배열은 크기를 가지는 내장 속성 length를 가짐   
// - 사용법은 `배열이름.length`   
- Array has built-in property length with size   
  - The method of use is `arrayName.length`   
   
- Example   
   
```java
public class Main {
    public static void main(String args[]) {
        int twoArray[][] = {{0, 1}, {10, 11, 12}};
        for (int i = 0; i < twoArray.length; i++)
            for (int j = 0; j < twoArray[i].length; j++)
                System.out.println(twoArray[i][j]);
    }
}
```
   
<br />
### String   
// 문자열   
   
#### String Class   
// String 클래스   
   
// String 클래스는 문자열을 표현하고 처리하기 위한 참조형   
// String형의 변수는 참조형이지만 기본형 변수처럼 사용할 수 있음   
- The String class is a reference type for representing and processing strings   
- A variable in the String type is a reference type, but can be used as a default type variable   
   
#### String literal   
// 문자열 리터럴 (상수)   
   
// 이중 따옴표를 사용함   
- Use double quotes   
   
```java
// 참조형 String 변수를 기본형처럼 다룸. 스택 영역 (Stack Area) 에 저장됨
// Treat the reference string variable like the default type. Stored in Stack Area
String s1 = "Java";

// 생성자를 사용하여 선언. 힙 영역 (Heap Area) 에 저장됨
// Declare using constructors. Stored in the Heap Area
String s2 = new String("Java");
```
   
// 참조형 변수에는 null이라는 특별한 값을 지정할 수 있음   
- A reference variable can be specified with a special value null   
   
```java
if (s1 != null) {
    ...
}
```
   
#### + Operator of String   
// 문자열의 + 연산자   
   
// 두 문자열을 연결하는 것   
- Connecting two strings   
   
// (문자열 + 기본형) 또는 (문자열 + 다른 참조형) 도 가능   
// - + 연산자를 사용할 때, 기본형 (또는 다른 참조형) 값은 문자열로 자동 형변환 가능   
- (String + Base Type) or (String + Other Reference Type) is also possible   
   - When using + operator, the base type (or other reference type) value can be automatically transformed into a string   
   
// print() 나 println() 에서 자주 사용됨   
// - 1개 매개변수를 문자열로 바꾸어 출력함   
// - System.out은 화면 출력을 위한 객체   
- Frequently used in print() or println()   
  - Outputs one parameter by replacing it with a string   
  - System.out is an object for screen output   
   
- Example   
   
```java
System.out.println("result=" + " " + result);
System.out.println('A' + 0);    // 'A' is a character
System.out.println("A" + 0);    // "A" is a string
```
   
- Result   
   
```java
result= XXX
65
A0
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
