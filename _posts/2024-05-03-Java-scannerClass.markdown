---
layout: post
title:  "Java: Scanner Class"
date:   2024-05-03 09:00:00 +0900
categories: [Java]
---

### Scanner Class   
// 스캐너 클래스   
   
// 키보드나 파일로부터 다양한 자료를 입력 받을 때 사용   
// - 기본적으로 공백 문자로 구분되는 단어 (토큰) 단위로 입력됨   
// - 문자열이나 기본형 값의 입력을 위해 next() 또는 nextInt() 와 같은 메소드를 제공함   
- Used to receive various data from a keyboard or file   
  - By default, entered in units of words (token) separated by spaces   
  - Provides methods such as next() or nextInt() for entering strings or base-type values   
   
// 키보드에서 입력을 받는 Scanner 객체 만들기   
// - System.in을 이용하여 Scanner 객체를 만들고 사용함   
- Create a scanner object that receives input from the keyboard   
  - Create and use scanner objects using System.in   
   
```java
Scanner sc = new Scanner(System.in);
String name = sc.next();
```
   
<br />
### Input using the scanner class   
// Scanner 클래스를 사용한 입력   
   
#### Method for input in the scanner class   
// Scanner 클래스의 입력용 메소드   
   
|Method|Description|
|:---|:---|
|boolean hasNext()|// 다음 단어가 있으면 true을 반환<br />- Returns true if the following word exist|
|String next()|// 다음 단어를 읽어 string으로 반환<br />- Read the following word and return them as string valuesg|
|boolean hasNextInt()|// 다음 단어가 int값이면 true를 반환<br />- Returns true if the following word is an int value|
|int nextInt()|// 다음 단어를 읽어 int값으로 반환<br />- Read the following word and return them as int values|
|boolean hasNextDouble()|// 다음 단어가 double값이면 true를 반환<br />- Returns true if the following word is an double value|
|double nextDouble()|// 다음 단어를 읽어 double값으로 반환<br />- Read the following word and return them as double values|
|boolean hasNextLine()|// 다음 라인이 있으면 true를 반환<br />- Returns true if the following line exist|
|String nextLine()|// 다음 라인을 읽어 string으로 반환<br />- Read the following line and return them as string values|
   
```java
Scanner s = new Scanner(System.in);
String name = s.next();
```
   
```java
import java.util.Scanner;

public class Main {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        while (sc.hasNextInt()) {
            System.out.println(sc.nextInt());
        }
    }
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
