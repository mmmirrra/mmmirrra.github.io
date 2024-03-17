---
layout: post
title:  "Database Systems: Modeling"
date:   2024-03-09 09:00:00 +0900
categories: [Database Systems]
---

### Understanding Database Modeling   
// 데이터베이스 모델링의 이해   
   
// 데이터베이스 모델링의 필요   
// - 비지니스적 관점 : 어떤 데이터를 저장해야 하는가?   
// - 컴퓨터 프로그래머 관점 : 어떻게 데이터를 저장해야 하는가?   
- Why Database Modeling is required   
  - Business Perspective : Data that needs to be stored?   
  - Computer Programmer's Perspective : Data that needs to be stored?   
   
<br />
### Database System Implementation Process   
// 데이터베이스 시스템 구현 과정   
   
|Application Implementation Process|Database Implementation Process|
|:---:|:---:|
|Functional requirements : Functional Analysis<br />↓<br />Application Program Design<br />↓ Application Architecture<br />Application Program Implementation<br />↓<br />Application|Analysis of user requirements<br />↓<br />Conceptual data modeling<br />↓<br />Logical data modeling<br />↓<br />Conceptual Schema<br />↓<br />Physical data modeling<br />↓<br />Internal Schema|
   
<br />
### Concept of Database Modeling   
// 데이터베이스 모델링의 개념   
   
// 데이터의 의미를 파악하고 데이터와 관여하는 업무 프로세스를 개념적으로 정의하고 분석하는 작업   
- The task of identifying the meaning of data and conceptually defining and analyzing the work processes involved in the data   
   
|Step of modeling|
|:---:|
|Analysis of user requirements<br />↓ → Data and Tasks<br />Conceptual data modeling<br />↓ → ER model<br />Logical data modeling<br />↓ → relational model<br />Conceptual Schema<br />↓<br />Physical data modeling<br />↓ → Physical Details<br />Internal Schema|
   
<br />
### Data Model   
// 데이터 모델   
   
// 사용할 데이터를 선별하여 데이터베이스에 체계적으로 구조화하여 저장·사용할 방법이 필요   
// - 데이터 모델 : 의미, 데이터 타입, 연산 등을 명시하기 위해 사용할 수 있는 개념들의 집합   
// - 데이터 모델링 : 실세계의 일부분을 DBMS가 지원하는 데이터 모델의 형태로 나타내는 과정   
- Need a method to select the data to use and systematically structure it in the database to store and use it   
  - Data model : a set of concepts that can be used to specify meanings, data types, operations, etc.   
  - Data modeling : The process of representing part of the real-world in the form of a DBMS-supported data model   
   
<br />
### Steps in Database Modeling   
// 데이터베이스 모델링의 단계   
   
// 1. 개념적 데이터 모델링   
// - 요구사항의 해석 오류를 방지   
// - 실세계의 데이터를 개념적으로 일반화시켜 데이터 구조, 데이터 타입, 속성, 관계, 제약조건 등을 이끌어내는 과정   
// 2. 논리적 데이터 모델링   
// - 특정 DBMS의 구현 모델에 맞춰 데이터를 표현하는 과정   
// - 데이터 정의 언어로 기술된 개념 스키마 생성   
// 3. 물리적 데이터 모델링   
// - 데이터베이스 파일의 내부 저장구조, 파일 구성, 인덱스, 접근 경로 등을 결정하는 과정   
1. Conceptual data modeling   
    - Avoid interpretation errors of requirements   
    - The process of conceptually generalizing real-world data to derive data structures, data types, attributes, relationships, constraints, etc.   
2. Logical data modeling   
    - The process of representing data according to the implementation model of a specific DBMS   
    - Creating a conceptual schema described in a data-defined language   
3. Physical data modeling   
    - The process of determining the internal storage structure, file composition, index, access path, etc. of a database file   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
