---
layout: post
title:  "Java: Package"
date:   2024-05-20 09:00:00 +0900
categories: [Java]
---

### Package   
// 패키지   
   
// 패키지는 관련이 있는 클래스와 인터페이스의 묶음   
// - 클래스와 인터페이스는 패키지의 멤버로 존재   
// - 패키지는 클래스와 인터페이스의 `.class` 파일이 저장된 폴더   
// 전체적으로 패키지는 계층 구조로 이루어짐   
// - 패키지 (폴더와 유사) 단위로 계층적으로 분류됨   
- Packages are a bundle of relevant classes and interfaces   
  - Classes and interfaces exist as members of the package   
  - The package is a folder where the `.class` file of the class and interface is stored   
- Overall, the package is hierarchical   
  - Hierarchically categorized in units of packages (like folders)   
   
#### Purpose of the Package   
// 패키지의 용도   
   
// 클래스를 쉽게 찾아 사용하기 위해서   
// 클래스의 이름 충돌을 피하기 위해서   
// - `graphics.Rectangle`과 `java.awt.Rectangle`   
// 클래스의 접근 범위를 제어하기 위해서   
- Use to easily find and use classes   
- Use to avoid class name conflicts   
  - `graphics.Rectangle` and `java.awt.Rectangle`   
- Use to control the access range of a class   
   
<br />
### System Package   
// 시스템 패키지   
   
// JDK가 제공하는 클래스 라이브러리   
// - JDK와 함께 설치됨   
// - 클래스 파일들은 기능에 따라 패키지로 묶여 분류됨   
// -- 과거에는 `jar` 파일로 압축되어 있었음 (예시 : `rt.jar`)   
// -- 최근 버전에는 모듈 단위로 분산되어 저장되어 있음   
// - `C:\Program Files\Java\jkd-21\lib\src.zip`에서 소스를 확인할 수도 있음   
- Class libraries provided by JDK   
  - Installed with JDK   
  - Class files are grouped into packages based on functionality   
    - In the past, it was compressed into a `jar` file (e.g., `rt.jar`)   
    - Recent versions are distributed and stored in units of modules   
  - Source can be found in `C:\Program Files\Java\jkd-21\lib\src.zip`   
   
<br />
### Using System Packages   
// 시스템 패키지의 사용   
   
// 가장 기본이 되는 최상위 시스템 패키지는 `java` 패키지임   
// - 대부분의 시스템 패키지는 `java.` 으로 시작됨   
// java 프로그램에서 상위 패키지와 하위 패키지의 구분을 위해 도트 ( . ) 를 사용   
// - 예시 : `java.lang, java.io, java.nio.file, java.util, java.util.stream` 등   
// - Java 언어에서 가장 기본적 클래스는 `java.lang` 패키지에 존재   
// - 프로그램에서 클래스를 사용할 때는 `java.io.IOException`과 같이 완전한 이름으로 표현하는 것이 원칙임   
- The most basic top-level system package is the `java` package   
  - Most system packages start with `java.`   
- Use dots ( . ) to distinguish between parent and child packages in the java program   
  - Example : `java.lang, java.io, java.nio.file, java.util, java.util.stream`, etc.   
  - The most basic class in Java language exists in the `java.lang` package   
  - When using a class in a program, it is a principle to express it in a complete name, such as `java.io.IOException`   
   
<br />
### User Packages   
// 사용자 정의 패키지   
   
#### Examples of User Package Definitions   
// 사용자 패키지 정의 예시   
   
```java
package com.vehicle;

public class Car {
    String szType = "car";
}
```
   
// 컴파일 결과로 `Car.class` 가 만들어짐   
// `Car.class` 는 `com.vehicle` 패키지에 저장됨   
// `com.vehicle` 는 어디에 있는지?   
// - 명령 프롬프트에서 컴파일 하는 경우 `-d` 옵션 사용하여 지정함   
// -- `> javac Car.java -d D:\javaClasses`   
// --- 이 경우 컴파일 결과 : `D:\javaClasses\com\vehicle\Car.class`   
// - 이클립스에서 컴파일하는 경우 컴파일 결과 : `작업공간\프로젝트폴더\bin\com\vehicle\Car.class`   
- `Car.class` is created as a result of compile   
- `Car.class` is stored in `com.vehicle` package   
- Where is `com.vehicle`?   
  - When compiling from a command prompt, specify using the `-d` option   
    - `> javac Car.java -d D:\javaClasses`   
      - In this case, compile results : `D:\javaClasses\com\vehicle\Car.class`   
  - Compile results when compiling from Eclipse : `workspace\projectFolder\bin\com\vehicle\Car.class`   
   
#### Define a user package in this clip   
// 이클립스에서 사용자 패키지 정의하기   
   
// 메뉴 `[File > New > Package]` 를 선택   
// - 패키지에 해당하는 폴더가 만들어짐   
// - 이후 생성된 패키지에서 클래스를 만들면 됨   
// 또는 메뉴 `[File > New > Class]` 를 선택하여 클래스 이름과 패키지 이름을 함께 입력함   
- Select the menu `[File > New > Package]`   
  - A folder corresponding to the package is created   
  - Then create a class from the generated package   
- Alternatively, select the menu `[File > New > Class]` to enter the class name and package name together   
   
<br />
### Using Packages and Classes   
// 패키지와 클래스의 사용   
   
// 다른 패키지에 존재하는 `public` 클래스를 사용하려면 기본적으로 패키지 경로를 포함한 완전한 클래스 이름을 사용해야 함   
// - 프로그램에서 여러 번 사용한다면 `import` 구문을 사용하는 게 좋음   
- To use a `public` class that exists in another package, you must use the complete class name, including the package path, by default   
  - It is recommended to use the `import` syntax if the program uses it multiple times   
   
- Example   
   
```java
graphics.Rectangle myRect = new graphics.Rectangle();
```
   
```java
java.util.Scanner s = new java.util.Scanner(System.in);
```
   
```java
import java.util.Scanner;

public class Main {
    public static void main(String args[]) {
        Scanner s = new Scanner(System.in);
    }
}
```
   
#### import   
   
// 1개 클래스 또는 패키지에 있는 클래스 전체를 `import` 할 수 있음   
- This can `import` a class or a whole class in a package   
   
```java
import packageName.*;
import packageName.className;
```
   
// `import` 구문은 소스 코드 맨 앞에 위치함   
// 단, `package` 구문이 있다면 그 다음에 위치함   
// 프로그램에서 패키지 경로를 생략하고, 이름만 가지고 클래스나 인터페이스를 사용할 수 있게 함   
- The `import` syntax is located at the beginning of the source code   
- However, if there is a `package` syntax, it is located in the next location   
- Program omits package path, allows classes or interfaces to be used only by name   
   
// Java 프로그램에서 `import java.lang.*;` 구문은 자동 포함되어 있음   
- Java program automatically contains the phrase `import java.lang.*;`   
   
<br />
### Package usage and access control   
// 패키지의 사용과 접근 제어   
   
// 다른 패키지에 존재하는 패키지 접근 수준 (`public` 이 생략된 클래스) 의 `Car 클래스`를 사용할 수 없음   
// - 같은 패키지에 정의하면 사용 가능   
- `Car class` of package access level (classes where `public` is omitted) existing in other packages is not available   
  - Available if defined in the same package   
   
```java
// 패키지 지정이 없으면 디폴트 패키지에 포함됨
// 문제가 없으려면 이 파일이 `Car 클래스`와 같은 패키지에 들어가야 함
// If no package is specified, it is included in the default package
// This file must be in the same package as 'Car Class' to avoid any problems
// package com.vehicle;

import com.vehicle.*;

class MyCar extends Car { }    // error
class MyBus extends Bus { }

public class Main {
    public static void main(String args[]) {
        Bus bus = new Bus();
        Car car = new Car();    // error
    }
}
```
   
```java
package com.vehicle;

// 패키지 접근 수준의 클래스. public이 생략된 클래스
// Classes at the package access level. Classes that omit public
class Car {
    ...
}
```
   
```java
package com.vehicle;

// public class
public class Bus extends Car {
    ...
}
```
   
<br />
### Finding Classes   
// 클래스 찾기   
   
// 컴파일하거나 실행할 때 필요한 클래스 `A` 를 찾아야 함   
// - 컴파일러가 `A.class` 가 위치한 경로 또는 `A.class` 를 포함하고 있는 `jar` 파일의 존재를 알아야 함   
// JVM은 기본 패키지가 확장 패키지 외에 사용자 클래스도 찾을 수 있음   
// - 이때 방법이 필요함   
- Need to find class `A` for compiling or running   
  - Compilers need to know the path where `A.class` is located or the existence of a file `jar` containing `A.class`   
- JVM base packages can find user classes in addition to extended packages   
  - Need a way at this time   
   
// 컴파일러는 환경변수 `CLASSPATH` 에 지정된 경로에서 사용자 클래스를 찾을 수 있음   
- Compilers can find user classes on paths specified in environment variable `CLASSPATH`   
   
// 환경변수 `CLASSPATH`   
// - `CLASSPATH` 의 경로는 `jar` 파일을 포함할 수 있음   
// - 예시 : 프로그램에서 `graphics.Circle` 클래스를 사용하는 경우   
// -- `CLASSPATH=경로;`라고 가정   
// --- 이때 `경로\graphics\Circle.class` 가 있어야 함   
// -- `CLASSPATH=a.jar`라고 가정   
// --- 이때 `a.jar`에서 `\graphics\Circle.class` 가 있어야 함   
// -- 이클립스에서는 `[프로젝트폴더 > Properties > Java Build Path > Libraries > Classpath]` 에서 추가함   
- Environment variable `CLASSPATH`   
  - Path of `CLASSPATH` may contain `jar` file   
  - Example : If the program uses the `graphics.Circle` class   
    - Assume that `CLASSPATH=path;`   
      - At this time, there must be a `path\graphics\Circle.class`   
    - Assume that `CLASSPATH=a.jar`   
      - At this time, there should be `\graphics\Circle.class` in `a.jar`   
    - This path adds from `[projectFolder > Properties > Java Build Path > Libraries > Classpath]`   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
