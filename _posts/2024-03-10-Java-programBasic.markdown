---
layout: post
title:  "Java: Program Basic - Creating Java Program"
date:   2024-03-10 09:00:00 +0900
categories: [Java]
---

### Java Program Example 1   
// Java 프로그램 예시 1   
   
// 2개의 클래스   
// 성적처리 프로그램 1   
- 2 classes   
- Grades Processing Program 1   
   
File Name : GradeOutputFirst.java   
   
```java
class Grade {
	int e;					// Variables for English grade
	int m;					// Variables for Mathematical grade
	
	void input_grade(int a, int b) {
		e = a;				// Enter English grade
		m = b;				// Enter Mathematical grade
	}
	void output_grade() {			// Output the sum of grades
		System.out.println(e + m);
	}
}

public class GradeOutputFirst {

	public static void main(String[] args) {
		Grade g1, g2;			// Expressing the grades of two people
		g1 = new Grade();		// Creating objects
		g2 = new Grade();
		
		g1.input_grade(90, 85);		// Enter grade
		g2.input_grade(80, 80);
		
		g1.output_grade();		// Grade output
		g2.output_grade();
	}

}
```
   
#### Result   
   
```cmd
175
160
```
   
<br />
### Java Program Example 2   
// Java 프로그램 예시 2   
   
// 1개의 클래스   
// 성적처리 프로그램 2   
- 1 class   
- Grades Processing Program 2   
   
File Name : GradeOutputSecond.java   
   
```java
public class GradeOutputSecond {

	int e;					// Variables for English grade
	int m;					// Variables for Mathematical grade
	
	void input_grade(int a, int b) {
		e = a;				// Enter English grade
		m = b;				// Enter Mathematical grade
	}
	
	void output_grade() {			// Output the sum of grades
		System.out.println(e + m);
	}

	public static void main(String[] args) {
		GradeOutputSecond g1, g2;		// Expressing the grades of two people
		g1 = new GradeOutputSecond();		// Creating objects
		g2 = new GradeOutputSecond();
		
		g1.input_grade(90, 85);			// Enter grade
		g2.input_grade(80, 80);
		
		g1.output_grade();			// Grade output
		g2.output_grade();
	}

}
```
   
#### Result   
   
```cmd
175
160
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
