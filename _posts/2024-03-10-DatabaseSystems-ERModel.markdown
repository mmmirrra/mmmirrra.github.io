---
layout: post
title:  "Database Systems: ER Model"
date:   2024-03-10 09:00:00 +0900
categories: [Database Systems]
---

### Concept of ER Model   
// ER 모델의 개념   
   
// 1976년 카네기 멜론 대학의 피터 첸 (Peter Chen) 박사 제안   
// 실세계의 속성들로 이루어진 개체(entity)와 개체 사이의 관계(relationship)를 정형화시킨 모델   
// 개념적 모델링 단계에서 사용되는 데이터 모델   
// 데이터 구조와 관계를 ER 다이어그램(ERD)으로 표현   
- Entity Relationship   
- 1976 Proposed by Dr. Peter Chen of Carnegie Mellon University   
- A model that formalized the relationship between objects and objects made up of real-world attributes   
- Data models used in the conceptual modeling phase   
- Data structures and relationships are represented as ER diagrams (ERD)   
   
// 구성요소   
// - 개체 집합   
// - 관계 집합   
// - 속성   
- Components   
  - Object set   
  - Relational sets   
  - Attributes   
   
<br />
### Components of the ER model   
// ER 모델 구성요소   
   
#### Object set   
// 개체 집합   

// 개체(entity)   
// - 실세계에 존재하는 다른 객체와 구별되는 유무형의 사물   
// - 개체를 설명하는 여러 속성들로 구성   
// - 예시   
// -- 학생번호 20230101-010101, 이름 홍, 성별 여자, 나이 20   
// 개체 집합(entity set)   
// - 같은 속성을 공유하는 개체들의 모임   
// - 예시   
- entity   
  - A tangible and intangible object that distinguishes it from other objects in the real-world   
  - consists of several attributes that describe an object   
  - Example   
    - Student number 20230101-010101, Name Hong, Gender Woman, Age 20
- entity set   
  - A group of objects that share the same attribute   
  - Example   
   
|Student|
|:---|
|Student number<br />Student name<br />Gender<br />Age()<br />...|
   
#### Relational sets   
// 관계 집합   

// 관계   
// - 개체와 개체 사이의 연관성   
// 관계집합   
// - 개체 집합 간의 연결 관계   
// - 예시   
- Relationship   
  - Object to object association   
- Relational sets   
  - Association relationships between sets of objects   
  - Example   
   
|Student|Relationship|Department|
|:---|:---:|:---|
|Student number<br />Student name<br />Gender<br />Age()<br />...|- ◇ -<br />Major|Department name<br />A college of law<br />...|
   
#### Attributes   
// 속성   

// 개체를 구체적으로 설명   
// 속성에 포함될 수 있는 값의 특성에 따라 여러 종류로 구분   
// 속성의 종류   
// - 단순 속성과 복합 속성   
// - 단일값 속성과 다중값 속성   
// - 유도 속성과 저장 속성   
- Describe the object specifically   
- Categorized into different types depending on the characteristics of the values that can be included in the attribute   
- Type of Properties   
  - Simple attributes and Compound attributes   
  - Single Value and Multiple Value Properties   
  - Derivation attributes and Storage attributes   
   
// 단순 속성   
// - 더 작은 구성요소로 나눌 수 없는 속성   
// - 예시   
- Simple attributes   
  - Properties that cannot be separated into smaller components   
  - Example   
   
|Student|
|:---|
|Student number<br />Student name<br />Gender<br />Age()<br />...|
   
// 복합 속성   
// - 더 작은 구성요소로 나눌 수 있는 속성   
// - 들여쓰기로 표기   
// - 예시   
- Compound attributes   
  - Properties that can be broken down into smaller components   
  - Indentify as indent   
  - Example   
   
|Student|
|:---|
|Date of birth<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;year<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;month<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;day<br />...|
   
// 단일값 속성   
// - 한 개체에 대해 단 하나의 값만을 갖는 속성   
// - 예시   
- Single Value   
  - Properties with only one value for one object   
  - Example   
   
|Student|
|:---|
|Student number<br />Student name<br />Gender<br />Date of birth<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;year<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;month<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;day<br />Age()<br />...|
   
// 다중값 속성   
// - 한 개체에 대해 여러 개의 값을 갖는 속성   
// - 예시   
- Multiple Value Properties   
  - Properties with multiple values for an object   
  - Example   
   
|Student|
|:---|
|{Phone number}<br />{Address}<br />...|
   
// 유도 속성   
// - 다른 속성의 값으로부터 값이 유추될 수 있는 속성   
// - 나이는 생년월일을 가지고 계산하여 유추할 수 있음   
// - 예시 : 나이는 생년월일을 가지고 계산하여 유추할 수 있음   
- Derivation attributes   
  - Properties where values can be inferred from values of other attributes   
  - Age can be inferred by calculating with date of birth   
  - Example : Age can be inferred by calculating with date of birth   
   
|Student|
|:---|
|Age()<br />...|
   
// 저장 속성   
// - 유도 속성을 위해 사용될 수 있는 속성   
// - 예시   
- Storage attributes   
  - Properties that can be used for derivation properties   
  - Example   
   
|Student|
|:---|
|Student number<br />Student name<br />Gender<br />Date of birth<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;year<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;month<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;day<br />...<br />{Phone number}<br />{Address}<br />...|
   
<br />
### Constraints   
// 제약조건   
   
// 데이터 모델은 데이터, 의미, 구조, 연관성 및 데이터의 조건을 표현하기 위한 도구   
// ER 모델은 개체와 관계에 대한 표현의 정확성을 위해 데이터가 준수해야 하는 제약조건을 정의할 수 있는 표현 방법을 제공   
- Data models are tools for representing data, meaning, structure, association, and conditions of data   
- The ER model provides a representation method to define the constraints that data must adhere to for the accuracy of representations about objects and relationships   
   
// 제약조건의 종류   
// - 사상수   
// - 참가 제약조건   
// - 키 속성   
- Types of constraints   
  - mapping cardinality   
  - participation constraints   
  - Key Property   
   
#### mapping cardinality   
// 사상수   

// 관계 집합에 참가한 개체 집합에 대해 한 개체가 다른 개체와 관계를 맺을 수 있는 수량을 명시   
// - 일대일(1 : 1)   
// - 일대다(1 : N)   
// - 다대일(N : 1)   
// - 다대다(N : N)   
- Specify how many objects one can relate to another for a set of objects that participate in a relational set   
  - One-to-One(1 : 1)   
  - One-to-Many(1 : N)   
  - Many-to-One(N : 1)   
  - Many-to-Many(N : N)   
   
Example of a one-to-one mapping cardinality representation   
// 일대일 사상수 표현 예시   
   
|Student|Relationship|Account|
|:---|:---:|:---|
|Student number<br />Student name<br />...|← ◇ →<br />possession|Account number<br />...|
   
Example of a one-to-many mapping cardinality representation   
// 일대다 사상수 표현 예시   
   
|Professor|Relationship|Subject|
|:---|:---:|:---|
|Professor number<br />Professor name<br />...|← ◇ -<br />Lecture|Subject code<br />Subject name<br />...|
   
Example of a many-to-many mapping cardinality representation   
// 다대다 사상수 표현 예시   
   
|Student|Relationship|Subject|
|:---|:---:|:---|
|Student number<br />Student name<br />...|- ◇ -<br />Registration for courses|Subject code<br />Subject name<br />...|
   
#### participation constraints   
// 참가 제약조건   

// 전체적 참가   
// - 어떤 대체 집합의 모든 개체가 관계 집합에 참여하는 조건   
// - 이중선 = 으로 표기   
// 부분적 참가   
// - 어떤 개체 집합의 일부 개체가 관계 집합에 참여하는 조건   
// - 단일선 - 으로 표기   
- An overall participation   
  - The condition that all objects in any alternate set participate in a relationship set   
  - Mark as a double line =   
- Partial participation   
  - Conditions under which some objects in a set of objects participate in a set of relationships   
  - Mark as a single line -   
   
|Professor|Relationship|Subject|
|:---|:---:|:---|
|Professor number<br />Professor name<br />...|← ◇ =<br />Lecture|Subject code<br />Subject name<br />...|
   
#### Key Property   
// 키 속성   

// 각 개체를 구별하는데 사용되는 유일한 값을 가지는 속성의 집합   
// - 개체를 고유하게 구분하는 역할   
// - 관계 집합의 특정 관계를 찾는 역할   
// 예시 : 학생번호는 학생마다 하나만 가질 수 있기 때문에 키가 될 수 있음   
- A set of attributes with a unique value used to distinguish each object   
  - Role of uniquely distinguishing objects   
  - Role of finding specific relationships in a set of relationships   
- Example : The student number can be a key because each student can have only one   
   
|Student|
|:---|
|<u>Student number</u><br />Student name<br />Gender<br />Age()<br />...|
   
#### Special Properties and Special Relationships   
// 특수 속성과 특수 관계   

// 관계 집합의 속성 : 두 개체 집합의 관계에서 생성되는 값을 저장하는 속성   
// 재귀적 관계 : 한 개체 집합이 자기 자신과 관계 집합을 형성하는 관계. 관계에 참가하는 개체가 행하는 기능을 개체의 역할(role)이라고 함   
// 예시   
// - 수강신청 시 발생하는 신청시각 이라는 값을 저장하고자 하면 발생하는 특수 속성과 특수 관계   
// - 과목 수강 시 먼저 학습하길 권장하는 선수과목이 있는 경우 과목이라는 동일한 객체 유형에서 과목코드를 참고해야하는 재귀적 관계가 발생함   
- Properties of Relationship Sets : Properties that store values that are generated by relationships between two sets of objects   
- Recursive relationship : A relationship in which a set of objects forms a set of relationships with itself. The function performed by an object participating in a relationship is called the role of the object   
- Example   
  - Special relationship with the special attributes that occur when you want to store the value of the application time that occurs when you register for a course   
  - If there is a prerequisite subject that is recommended to be studied first when taking a subject, a recursive relationship occurs in which the subject code should be referenced in the same object type called the subject   
   
|Student|Relationship|Subject|Recursive<br />relationship|
|:---|:---:|:---|---:|
|Student number<br />Student name<br />...|Application time<br />│<br />- ◇ -<br />Registration<br />for courses|Subject code<br />Subject name<br />...<br />Preceding<br />subject code<br />...|← Subject code<br />│<br />│<br />- Preceding  - ◇<br />subject code &nbsp;&nbsp;&nbsp;<br /><br />|
   
// 약한 개체 집합   
// - 개체의 존재 유무가 관계를 맺고 있는 개체의 존재에 종속되는 개체 집합   
// - 약한 개체 집합은 1：N 관계 집합을 통해 강한 개체 집합에 연결해야 하며, 약한 개체 집합의 구별자(또는 부분키)는 약한 개체 집합 내의 개체들을 구분하는 속성의 집합임   
// - 따라서 약한 개체 집합의 키 설정은 반드시 지배 개체 집합의 키와 약한 개체 집합의 부분키로 구성되어야 함   
// 강한 개체 집합   
// - 약한 개체 집합과 연결되어 있는 일반 개체 집합   
// 예시   
// - 학생 객체가 없어지면 계좌 객체도 사라지므로 계좌는 약한 개체 집합임   
// - 계좌 객체가 없어져도 학생 객체는 사라지지 않으므로 학생은 강한 개체 집합임   
- A weak set of objects   
  - A set of objects whose existence depends on the existence of the object it is associated with   
  - A weak set of objects must be associated to a strong set of objects through a 1 : N relationship set, and a discriminator (or subkey) of a weak set of objects is a set of attributes that distinguish objects within a weak set of objects   
  - Therefore, the key setting of the weak object set must consist of the key of the parent object set and the subkey of the weak object set   
- A strong set of objects   
  - General set of objects associated with a weak set of objects
- Example   
  - An account is a weak set of objects because when a student object disappears, the account object also disappears   
  - The student object disappears when the account object disappears, so the student is a strong set of objects   
   
|Student|Relationship|Account|
|:---|:---:|:---|
|<u>Student number</u><br />Student name<br />...|← ◈ →<br />possession|<u>Account number</u><br />Balance<br />...|
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
