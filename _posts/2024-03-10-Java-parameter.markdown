---
layout: post
title:  "Java: Command line Parameter"
date:   2024-03-10 09:00:00 +0900
categories: [Java]
---

### Command line parameter   
// 명령행 매개변수   
   
// 프로그램을 실행할 때 전달하는 인자   
// main() 함수에 전달되는 인자   
// 문자열로 전달됨   
- Arguments passed when running a program   
- Arguments passed to the main() function   
- Forwarded as a string   
   
```java
public class Main {

	public static void main(String[] args) {
		System.out.println("Hello");
		System.out.println(args[0] + ", " + args[1]);
	}

}
```
   
#### Run the class file in the bin folder in the command prompt window   
// 명령 프롬프트 창에서 bin 폴더의 class 파일 실행   
   
```cmd
java Main test1 test2
```
   
- Result   
   
```
Hello
test, test2
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
