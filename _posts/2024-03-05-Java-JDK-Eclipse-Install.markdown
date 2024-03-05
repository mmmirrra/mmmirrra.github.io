---
layout: post
title:  "Java: JDK and Eclipse Install"
date:   2024-03-05 09:00:00 +0900
categories: [Java]
---

### Downloading and Installing JDK   
// JDK의 다운로드와 설치   
   
#### JDK (Java Development Kit)   
// JKD 또는 Java SDK는 'Java 플랫폼과 개발도구'의 묶음임   
// - 개발도구 : 컴파일러, 디버거, 문서도구 등   
// Java 홈페이지에서 다운로드하여 설치할 수 있음   
// - https://www.oracle.com/java   
// - 자신이 사용하는 운영체제에 맞는 것을 선택   
// 명령 프로프트에서 java 명령어 실행하여 JDK가 설치됐는지 확인   
- JKD or Java SDK is a bundle of 'Java Platforms and Development Tools'   
  - Development tools : Compiler, Debugger, Document Tools, etc.
- You can download and install from the Java homepage   
  - https://www.oracle.com/java   
  - Choose based on the operating system you use   
- Verify JDK is installed by running the java command in a command prompt   
   
<br />
#### JDK installation process   
// JDK 설치과정 따라하기   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk1.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk2.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk3.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk4.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk5.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk6.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk7.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk8.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk9.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk10.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaJdk11.png)
   
<br />
#### Environment Variable   
// 환경변수   
   
// JDK 예전 버전은 환경변수를 설정해야 사용할 수 있음. 최신 버전은 환경변수 설정을 하지 않아도 사용 가능   
// PATH 변수에 아래 경로를 추가   
// - C:\Program Files\Java\jdk-21\bin   
// JDK_HOME 변수에 JDK 설치 폴더 경로를 추가   
// - C:\Program Files\Java\jdk-21   
- JDK older versions were available with environmental variables set. The latest version is available without setting environment variables   
- Add the path below to the PATH variable   
  - `C:\Program Files\Java\jdk-21\bin`   
- Add JDK installation folder path to JDK_HOME variable   
  - `C:\Program Files\Java\jdk-21`   
   
<br />
#### Setting Environment Variables   
// 환경변수 설정 따라하기   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEnvironmentVariable1.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEnvironmentVariable2.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEnvironmentVariable3.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEnvironmentVariable4.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEnvironmentVariable5.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEnvironmentVariable6.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEnvironmentVariable7.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEnvironmentVariable8.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEnvironmentVariable9.png)
   
<br />
#### Running Java Programs After JDK Installation   
// JDK 설치 후 Java 프로그램 실행   
   
// 소스 작성을 위해 텍스트 편집기 사용   
// 명령 프롬프트 창에서 컴파일 명령은 javac   
// - 예시 : Javac Hello.java   
// 명령 프롬프트 창에서 실행 명령은 java   
// - 예시 : java Hello   
- Using a text editor to create a source   
- In the Command Prompt window, compilation commands are javac   
  - Example   
   
    ```cmd
    Javac Hello.java
    ```
   
- In the Command Prompt window, the executable command is java   
  - Example   
   
    ```cmd
    java Hello
    ```
   
<br />
### Installing Eclipse   
// 이클립스 설치   
   
#### Eclipse   
// 이클립스   
   
// 무료 오픈소스 프로그램 개발도구   
// Eclipse IDE for Java Developers를 설치해야 함   
// 이클립스 홈페이지에서 다운로드하여 설치할 수 있음   
// - 설치용 파일(.exe) 또는 압축 파일(.zip)을 다운로드함   
// - 압축만 풀면 설치가 완료되는 것임   
// 설치 과정에서 작업공간(workspace) 폴더를 정해야 함   
// - 작업 공간은 프로젝트 폴더, 소스 코드, 클래스 파일 등을 저장하는 장소   
- Free Open Source Program Development Tool   
- 'Eclipse IDE for Java Developers' must be installed   
- You can download and install from the Eclipse homepage   
  - Download an executable (.exe) or a compressed (.zip) file   
  - The installation is complete by simply decompressing   
- The installation process requires a workspace folder to be determined   
  - A workspace is a place to store project folders, source code, class files, etc.   
   
<br />
#### Eclipse Installation Process   
// 이클립스 설치과정 따라하기   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEclipse1.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEclipse2.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEclipse3.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEclipse4.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEclipse5.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaEclipse6.png)
   
<br />
### Develop Java programs using Eclipse   
// 이클립스를 사용하여 Java 프로그램 개발하기   
   
// 1. 이클립스에서 Java Project를 생성   
// - '메뉴 : File -> New -> Java Project' 선택   
// 2. '메뉴 : Window -> Show View -> Package Explorer' 선택하여 탐색기를 열고, 탐색기에서 클래스가 저장될 패키지를 생성   
// - 탐색기에 있는 프로젝트에 마우스 오른쪽 버튼으로 'New -> Package' 선택   
// 3. 패키지 안에 클래스를 생성   
// - Java 프로그램은 클래스 단위로 작성함   
// - 탐색기에 있는 패키지 이름에 마우스 오른쪽 버튼으로 'New -> Class' 선택   
// - 클래스의 이름으로 파일 이름(.java)이 정해짐   
// 4. Java 소스를 저장하면 컴파일이 자동으로 실행됨. 컴파일 시 클래스마다 .class 파일이 자동으로 생성됨   
// 5. main() 메소드를 가진 클래스를 실행   
1. Creating a Java Project in Eclipse   
    - Select 'Menu : File -> New -> Java Project'   
2. Select 'Menu : Window -> Show View -> Package Explorer' to open the Explorer, and create a package in Explorer for class to be stored   
    - Right-click the project in Explorer and select 'New -> Package'   
3. Create class in a package   
    - Java program is written on a class-by-class basis   
    - Right-click the package name in Explorer and select 'New -> Class'   
    - Set file name (.java) as class name   
4. Saving a Java source causes compilation to run automatically. Class (.class) files are automatically created for each class during compilation   
5. Run a class that contains the main() method   
   
<br />
#### Try developing Java program   
// Java 프로그램 개발 따라하기   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example1.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example2.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example3.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example4.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example5.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example6.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example7.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example8.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example9.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example10.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example11.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example12.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example13.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example14.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example15.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example16.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example17.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example18.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example19.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example20.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example21.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example22.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example23.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example24.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example25.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example26.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example27.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example28.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example29.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example30.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example31.png)
<br />
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/javaProject1_example32.png)
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
