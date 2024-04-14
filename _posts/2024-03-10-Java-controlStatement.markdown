---
layout: post
title:  "Java: Conditional Statement - Control Structure - if / switch / for / break / continue"
date:   2024-03-10 09:00:00 +0900
categories: [Java]
---

### Type of sentence   
// 문장의 종류   
   
// 수식문   
// - 수식은 변수, 연산자, 함수호출 등으로 구성되며, 결과값을 계산함   
// - 대입문, 증가문, 함수호출문, 객체생성문 등   
// 변수 선언문   
// 제어문   
// - 선택문, 반복문, 점프문   
// 기타   
// - 블록문   
// -- 여러 문장을 중괄호로 묶은 것을 블록이라 함   
// -- `{ ... }`   
// - 레이블문   
// -- `레이블 : 문장`   
// - 예외처리문   
// -- `try-catch 문`   
// - 동기화문   
// -- `synchronized { 블록문 }`   
- numeric expression statement   
  - The numeric expression of variables, operators, function calls, etc., and calculates the resulting value   
  - substitute statement, increment statement, function call statement, object creation statement, etc.   
- variable declaration statement   
- control statement   
  - Selective statements, loop statements, and jump statements   
- etc.   
  - block statements   
    - Blocks are the combination of multiple sentences in brace   
    - `{ ... }`   
  - label statement   
    - `label : sentence`   
  - Exception statement   
    - `try-catch`   
  - synchronization statement   
    - `synchronized { block }`   
   
<br />
### control statement   
// 제어문   
   
// 프로그램의 실행 흐름   
// - 프로그램의 실행은 기본적으로 위에서 아래로 순차 실행됨   
// - 제어문은 실행 흐름을 바꿈   
- Program running flow   
  - Programs run sequentially from top to bottom by default   
  - Control statements change running flow   
   
Type of control statement   
// 제어문의 종류   
   
|Type|Description|
|:---|:---|
|selective statement|Select a statement based on a condition<br />- if, switch|
|loop statement|a repetition of a statement according to a condition<br />- for, while, do-while|
|jumping statement|branch statement<br />- return, break, continue|
   
<br />
### selective statement   
// 선택문   
   
#### if   
   
// `if (boolean-수식) 문장`   
`if (boolean-numeric expression) sentence`   
   
#### if-else   
   
// `if (boolean-수식 문장) else 문장`   
`if (boolean-numeric expression sentence) else sentence`   
   
#### matching if and else   
// if와 else의 짝짓기   
   
// else는 짝이 없는 가장 가까운 if와 짝을 이룸   
- else is paired with the nearest if   
   
```java
int a = 2;
int b = 2;

if (a == 1)
{
    if (b == 2)
        System.out.println("a was 1 and b was 2");
}
else
{
    System.out.println("a wasn't 1");
}
```
   
#### switch   
   
// 다중 선택 구조   
// case 조건은 정수 (long형 제외) 와 호환되거나 String 값   
// default는 생략 가능하며, 어떤 case에도 해당되지 않는 경우 매칭됨   
// 만족되는 case를 실행한 후, break문을 만날 때까지 계속 실행   
- Multiple select structure   
- Case conditions are compatible with integers (excluding long types) or are string values   
- The default is optional and is matched if it does not apply to any case   
- After executing the satisfied case, continue until the break statement is met   
   
```java
switch (n) {
    case 10:
        System.out.println("It's 10");
        break;
    case 20:
    case 30:
        System.out.println("It's either 20 or 30");
        break;
    default:
        System.out.println("I don't know");
        break;
}
```
   
#### enhanced for loop statement   
// 향상된 for문   
   
// for-each문   
// 배열이나 컬렉션의 원소들을 차례로 다룰 때 편리   
// 형식은 `for (변수선언 : 배열) { 문장... }`   
- for-each   
- Convenient to handle the elements of an array or collection in turn   
- The format is `for (variable declaration : array) {sentence...}`   
   
```java
int[] arrayOfInts = { 32, 87, 3, 589, 12, 1076, 2000, 8};
for (int element : arrayOfInts) {
    System.out.print(element + " ");
}
System.out.println();
```
   
#### Result   
   
```java
32 87 3 589 12 1076 2000 8

```
   
<br />
### jumping statement   
// 점프문   
   
#### break statement   
// break문   
   
// break문을 포함하는 가장 가까운 switch문, for문, while문, do-while문의 실행을 끝냄   
// - 반복문이나 switch문을 빠져나갈 때 사용   
// 형식은 `break;`   
- End execution of the nearest switch statement, for statement, while statement, do-while statement including break statement   
  - Used to exit loop statement or switch statements   
- The format is `break;`   
   
// 레이블을 사용하면 특정 블록 또는 특정 반복문을 빠져나갈 수 있음   
// - 중첩 for문에서 바깥 for문을 종료하는 경우   
// - 이 경우 형식은 `break 레이블;`   
// -- 반복문에 레이블을 지정하려면 `레이블 : 반복분`   
- Labels exit specific block or specific loop statement   
  - To exit an outer for statement from a nested for statement   
  - The format is `break label;`   
    - To label loop statements : `label : loop`   
   
#### continue statement   
// continue문   
   
// 반복문 안에서 사용함   
// 가장 가까이 있는 반복문의 다음 반복을 위한 조건식으로 즉시 제어를 이동하기 위한 것   
// 형식은 `continue;`   
- Used in a loop statement   
- To move control immediately as a conditional expression for the next loop statement of the nearest loop statement   
- The format is `continue;`   
   
// 레이블을 사용하여 특정 반복문의 다음 반복으로 이동할 수 있음   
// - 중첩 for문에서 바깥 for문의 다음 반복으로 갈 때   
// - 이 경우 형식은 `continue 레이블;`   
// -- 반복문에 레이블을 지정하려면 `레이블 : 반복분`   
- Use a label to move a particular loop statement to the next loop   
  - To go from nested for statements to the next loop of outer for statements   
  - The format is `continue label;`   
    - To label loop statements : `label : loop`   
   
```java
public class Main {
    public static void main(String[] args) {
        int nSum = 0;
        my_loop: for (int i = 1; i <= 10; i++) {
            if (i % 2 == 0)
                continue my_loop;
            nSum += i;
        }
        System.out.println(nSum);
    }
}
```
   
#### Result   
   
```java
25
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
