---
layout: post
title:  "Database Systems: Relational Model"
date:   2024-04-03 09:00:00 +0900
categories: [Database Systems]
---

### Concept of relational model   
// 관계형 모델의 개념   
   
#### Logical Data Modeling Steps   
// 논리적 데이터 모델링 단계   
   
// 1. DBMS에서 사용하는 데이터 모델에 맞추어 데이터를 표현하는 과정   
// 2. 데이터 정의 언어로 기술된 개념 스키마 생성   
// 3. 관계형 모델(relational model)   
// -- 1969년 에드가 F.코드에 의해 제안   
// -- 릴레이션(relation)으로 데이터를 표현하는 모델   
// -- 데이터 표현이 단순하고 직관적 구조화 모델   
// -- 현재 대다수 DBMS의 기초   
// --- 관계형 모델을 사용하는 관계형 DBMS (RDMBS)   
// --- Oracle, DB2, PostgreSQL, MySQL, MSSQL 등   
1. The process of representing data according to the data model used by DBMS   
2. Create a conceptual schema described in a data-defined language   
3. Relational Model   
    - Proposed by Edgar F. Code, 1969   
    - Models that represent data with relation   
    - Simple data representation and intuitive structuring model   
    - The foundation of most DBMSs today   
      - Relational DBMS Using Relational Models (RDMBS)   
      - Oracle, DB2, PostgreSQL, MySQL, MSSQL, etc.   
   
// 논리적 데이터 모델링의 필요   
// - 관계형 DBMS(RDBMS)의 구현 모델에 맞춰 데이터의 구조와 관계를 표현   
// - 작성된 ERD를 RDBMS가 수용 가능한 구조로 변환   
- Why logical data modeling is necessary   
  - Express the structure and relationship of data in line with the implementation model of relational DBMS (RDBMS)   
  - Converting created ERD into a structure acceptable to RDBMS   
   
#### Composition of Relation   
// 릴레이션의 구성   
   
// 두 개의 메타 데이터를 이용해서 하나의 값을 표현   
// 이차원 구조   
// 스키마 : 표 머리   
// 컬럼, 속성, 필드 : 스키마의 항목. 열   
// 레코드, 투플 : 스키마에 맞춰 채워진 값 모임. 행   
// 컬럼값 : 컬럼과 레코드가 만나는 곳의 값. 셀   
// 인스턴스 : 특정 시점에 릴레이션 스키마에 맞춰서 레코드가 들어가 있는 상태   
- Express one value using two metadata   
- Two-dimensional structure   
- Schema : Table Head   
- Column, Properties, Fields : Items in Schema. Column   
- Record, Tuple : Set of values filled to schema. Row   
- Column value : The value where the column meets the record. Cell   
- Instance : The state in which records are placed according to the relation schema at a certain point in time   
   
#### Characteristics of Relation   
// 릴레이션의 특징   
   
// 레코드의 유일성   
// - 중복된 레코드의 존재가 불가능   
// 레코드의 무순서성   
// - 레코드의 순서는 의미가 없음   
// 컬럼의 무순서성   
// - 컬럼은 순서가 없고, 이름과 값의 쌍   
// 컬럼값의 원자성   
// - 모든 값들은 나눌 수 없는, 단 하나의 의미   
- The uniqueness of the record   
  - Unable to exist duplicate records   
- Unorderedness of a record   
  - The order of records is meaningless   
- Unorderedness of a column   
  - Columns are not ordered, with a name-value pair   
- Atomicity of column values   
  - All values are indivisible, one meaning   
   
#### Role of the Key   
// 키(Key)의 역할   
   
// 릴레이션의 레코드를 유일하게 식별할 수 있는 값을 가지고 있는 컬럼   
- A column that has the only identifiable value for a relation's record   
   
#### Key Properties   
// 키의 속성   
   
// 유일성   
// 최소성   
- Uniqueness   
- Irreducibility   
   
#### Key Types   
// 키의 종류   
   
// 수퍼키 : 유일성 만족   
// 후보키 : 유일성, 최소성 만족   
// 기본키 : 레코드의 구분을 위해 선택된 후보키   
// 외래키 : 참조된 다른 릴레이션의 기본키. 두 릴레이션에 포함된 레코드 간 연관성을 표현   
- super key : Satisfied with Uniqueness   
- candidate key : Uniqueness, Irreducibility satisfaction   
- PK (primary key) : Candidate key selected for distinguishing records   
- FK (foreign key) : Primary key for other referenced relations. Expressing the association between records contained in both relations   
   
#### Constraints of Relational Models   
// 관계형 모델의 제약조건   
   
// 영역 제약조건   
// - 컬럼에 정의된 영역(domain)에 속한 값으로만 컬럼값이 결정   
// 키 제약조건   
// - 키는 레코드를 고유하게 구별하는 값으로 구성   
// 개체 무결성 제약조건   
// - 어떠한 기본키 값도 널(null)이 될 수 없음   
// 참조 무결성 제약조건   
// - 반드시 존재하는 레코드의 기본키만 참조 가능   
- Area Constraints   
  - The column value is determined only by the value that belongs to the domain defined in the column   
- Key Constraints   
  - The key consists of values that uniquely distinguish the record   
- Object Integrity Constraints   
  - No default key value can be null   
- Reference Integrity Constraints   
  - Only the default keys of existing records can be referenced   
   
#### The concept of NULL   
// 널(NULL)의 개념   
   
// '없음' 또는 '0'이 아닌 미지의 값에 대한 표현   
// - 입력된 적이 없는 값   
// - 적용 불가능한 값   
- Expression for unknown values other than 'none' or '0'   
  - A value that has never been entered   
  - Non-applicable value   
   
<br />
### Conversion of ERD   
// ERD의 변환   
   
#### To convert to a relational model   
// 관계형 모델로 변환 방법   
   
// 단계 1. 개체 집합 : 개체 집합은 릴레이션으로 변환   
// 단계 2. 약한 개체 집합 : 강한 개체 집합의 키 속성을 약한 개체 집합의 릴레이션에 포함   
// 단계 3. 일대일 관계 : 두 릴레이션 중에서 한 릴레이션의 기본키를 다른 릴레이션에서 외래키로 참조   
// 단계 4. 일대다 혹은 다대일 관계 : '일'쪽의 기본키를 '다'쪽 릴레이션에서 외래키로 참조   
// 단계 5. 다대다 관계 : 관계 릴레이션을 생성하고, 두 릴레이션의 기본키를 각각 참조하는 외래키를 복합키 형태의 컬럼으로 구성   
// 단계 6. 다중값 속성 : 릴레이션의 기본키를 참조하는 외래키와 다중값 속성으로 별도의 릴레이션으로 구성   
// 단계 7. 관계 집합의 속성 : 외래키가 위치한 릴레이션의 컬럼으로 삽입   
- Step 1. Object Set: Convert object set to relation   
- Step 2. Weak Object Set: Include key properties of strong object sets in the relation of weak object sets   
- Step 3. One-to-one relationship: Refer to the primary key of one of the two relationships as the foreign key in the other   
- Step 4. One-to-many or many-to-one relationship: Refer to the basic key on the 'one' side as a foreign key in the 'many' side reference   
- Step 5. Many-to-many relationship: Create a relational relationship, and organize the foreign keys that refer to the primary keys of the two relationships into columns in the form of composite keys   
- Step 6. Multi-value properties: Composes of a foreign key that refers to the primary key of the relationship and a separate relationship with a multi-value property   
- Step 7. Properties of the relational set: Insert into the column of the relation where the foreign key is located   
   
#### Conversion Case of ER Diagram 1 - One-to-Many(1 : N) relationship   
// ER 다이어그램의 변환 케이스 1 - 일대다(1 : N) 관계   
   
- ER Model   
   
|Professor|Relationship|Subject|
|:---|:---:|:---|
|<u>Professor number</u><br />Professor name<br />Position<br />Annual salary|← ◇ =<br />Lecture|<u>Subject code</u><br />Subject name<br />Credit|
   
- Professor Relation   
   
|Professor number(PK)|Professor name|Position|Annual salary|
|:---|:---|:---|:---|
   
- Subject Relation   
   
|Subject code(PK)|Subject name|Credit|Professor number(FK)|
|:---|:---|:---|:---|
   
#### Conversion Case of ER Diagram 2 - Many-to-Many(N : N) relationship   
// ER 다이어그램의 변환 케이스 2 - 다대다(N : N) 관계   
   
- ER Model   
   
|Student|Relationship|Subject|
|:---|:---:|:---|
|<u>Student number</u><br />Student name<br />Birthday<br />Age<br />Phone number|Application time<br />│<br />- ◇ -<br />Registration<br />for courses|<u>Subject code</u><br />Subject name<br />Credit|
   
- Student Relation   
   
|Student number(PK)|Student name|Birthday|Age|Phone number|
|:---|:---|:---|:---|:---|
   
- Subject Relation   
   
|Subject code(PK)|Subject name|Credit|
|:---|:---|:---|
   
- Course Relationship Set Relation   
  - Only in a set of many-to-many relationships does that set turn into a relation   
   
|Student number(PK, FK)|Subject code(PK, FK)|Application time|
|:---|:---|:---|
   
#### Conversion Case of ER Diagram 3 - One-to-One(1 : 1) relationship. A weak set of objects   
// ER 다이어그램의 변환 케이스 3 - 일대일(1 : 1) 관계. 약한 개체 집합   
   
- ER Model   
   
|Student|Relationship|Account|
|:---|:---:|:---|
|<u>Student number</u><br />Student name<br />Birthday<br />Age<br />Phone number|← ◈ →<br />possession|<u>Account number</u><br />Balance|
   
- Student Relation   
   
|Student number(PK)|Student name|Birthday|Age|Phone number|
|:---|:---|:---|:---|:---|
   
- Account Relation   
   
|Account number(PK)|Balance|Student number(PK, FK)|
|:---|:---|:---|
   
<br />
### Data Operation   
// 데이터 연산   
   
#### Concept of relational operation   
// 관계 연산의 개념   
   
// 관계형 모델을 기반으로 구성된 릴레이션을 사용하여 새로운 릴레이션을 생성하는 표현   
// 사용자의 관점에서 필요한 데이터를 릴레이션에서 추출하는 방법을 제공하는 도구   
- Representations that generate new relations using relations constructed based on relational models   
- A tool that provides a way to extract the necessary data from a relationship from the user's point of view   
   
// 관계 대수 (relational algebra)   
// - 관계 연산을 정의하는 방법   
// - 주어진 릴레이션에서 필요한 릴레이션을 만드는 연산자(∪, ∩, －, σ, π, ×, ⋈, ÷, 집계함수 등)로 구성   
// - 관계 대수 연산자는 새로운 임시 릴레이션을 생성   
// - 연산자를 중첩하여 연산 처리 절차를 표현   
- relational algebra   
  - To define relational operation   
  - It consists of operators (∪, ∩, -, σ, π, ×, ×, ⋈, ÷, Aggregation Function, etc.) that create the necessary relations for a given relation   
  - The relational algebra operator creates a new temporary relation   
  - Overlapping operators to represent operational processing procedures   
   
<br />
### Relational algebra operator   
// 관계 대수 연산자   
   
#### Select operation   
// 셀렉트 연산   
   
// 주어진 릴레이션에서 조건을 만족하는 레코드를 갖는 릴레이션을 생성   
- Create a relationship with a record that satisfies the condition in a given relationship   
  - σ <sub>condition</sub> (R)   
   
// 조건 : a ⊝ b 또는 a ⊝ v   
- Condition: a ⊝ b or a ⊝ v   
   
|a, b|Property name|v|constant value|
|:---:|:---:|:---:|:---:|
|<b>⊝</b>|<b>Comparator {＝, ≠, ＜, ＞, ≤, ≥</b>}|<b>R</b>|<b>Relation</b>|
   
- Combination of conditions : ∧(and), ∨(or)   
   
#### Examples of Select Operation   
// 셀렉트 연산의 예시   
   
- Professor Relation   
   
|Professor number|Professor name|Position|Department of affiliation|Annual salary|
|:---:|:---:|:---:|:---|---:|
|100-0001|Choi|Professor|Life Science|80,000,000|
|200-0002|Han|Associate Professor|Life Science|60,000,000|
|300-0003|Park|Assistant Professor|Life Science|40,000,000|
|100-0004|Kim|Professor|Computer Science|80,000,000|
|300-0005|Jung|Assistant Professor|Computer Science|40,000,000|
|100-0006|Lee|Professor|Law|80,000,000|
|100-0007|Hwang|Professor|Public Administration|80,000,000|
   
- σ <sub>Department of affiliation = 'Computer Science'</sub> (Professor Relation)   
   
|Professor number|Professor name|Position|Department of affiliation|Annual salary|
|:---:|:---:|:---:|:---|---:|
|100-0004|Kim|Professor|Computer Science|80,000,000|
|300-0005|Jung|Assistant Professor|Computer Science|40,000,000|
   
- σ <sub>Department of affiliation = 'Computer Science' ∧ Annual salary ≥ 50,000,000</sub> (Professor Relation)   
   
|Professor number|Professor name|Position|Department of affiliation|Annual salary|
|:---:|:---:|:---:|:---|---:|
|100-0004|Kim|Professor|Computer Science|80,000,000|
   
#### Project Operation   
// 프로젝트 연산   
   
// 기술된 컬럼만 갖는 릴레이션으로 재구성   
- Reconfiguring to Relation with Only Described Columns   
  - π <sub>＜column list＞</sub> (R)   
   
// ＜컬럼리스트＞ : A<sub>1</sub>, A<sub>2</sub>, ..., A<sub>n</sub>와 같이 R에 존재하는 컬럼을 ,(콤마)로 분리하여 기술   
- ＜column list＞ : Describes the columns present in R as commas(,), such as A<sub>1</sub>, A<sub>2</sub>, ..., A<sub>n</sub>   
   
#### Examples of Project Operation   
// 프로젝트 연산의 예시   
   
- Professor Relation   
   
|Professor number|Professor name|Position|Department of affiliation|Annual salary|
|:---:|:---:|:---:|:---|---:|
|100-0001|Choi|Professor|Life Science|80,000,000|
|200-0002|Han|Associate Professor|Life Science|60,000,000|
|300-0003|Park|Assistant Professor|Life Science|40,000,000|
|100-0004|Kim|Professor|Computer Science|80,000,000|
|300-0005|Jung|Assistant Professor|Computer Science|40,000,000|
|100-0006|Lee|Professor|Law|80,000,000|
|100-0007|Hwang|Professor|Public Administration|80,000,000|
   
- π <sub>Professor name, Department of affiliation</sub> (Professor Relation)   
   
|Professor name|Department of affiliation|
|:---:|:---|
|Choi|Life Science|
|Han|Life Science|
|Park|Life Science|
|Kim|Computer Science|
|Jung|Computer Science|
|Lee|Law|
|Hwang|Public Administration|
   
#### Utilization of relational algebraic operational expressions   
// 관계 대수 연산식의 활용   
   
// Q. 직위가 '부교수'인 교수의 교수이름을 출력하라   
Q. Print out the name of the professor whose position is 'Associate Professor'   
   
- Professor Relation   
   
|Professor number|Professor name|Position|Department of affiliation|Annual salary|
|:---:|:---:|:---:|:---|---:|
|100-0001|Choi|Professor|Life Science|80,000,000|
|200-0002|Han|Associate Professor|Life Science|60,000,000|
|300-0003|Park|Assistant Professor|Life Science|40,000,000|
|100-0004|Kim|Professor|Computer Science|80,000,000|
|300-0005|Jung|Assistant Professor|Computer Science|40,000,000|
|100-0006|Lee|Professor|Law|80,000,000|
|100-0007|Hwang|Professor|Public Administration|80,000,000|
   
- π <sub>Professor name</sub> (σ <sub>Position = 'Associate Professor'</sub> (Professor Relation))   
   
|Professor name|
|:---:|
|Han|
   
#### Set Operator   
// 집합 연산자   
   
// 수학적 집합 이론에서의 이진 연산   
// - 합집합 : R ∪ S   
// - 교집합 : R ∩ S   
// - 차집합 : R － S   
- Binary operation in mathematical set theory   
  - union set : R ∪ S   
  - intersection set : R ∩ S   
  - difference set : R － S   
   
// 릴레이션은 집합, 레코드는 집합에 포함된 원소   
- Relation is a set, Records are elements in a set   
   
// 집합 연산자 사용 조건   
// - 릴레이션 R과 S의 차수가 동일   
// - 모든 i에 대해 R의 i번째 컬럼의 도메인과 S의 i번째 컬럼의 도메인이 반드시 동일   
- Set operator usage conditions   
  - Relation R and S have the same order   
  - For all i, the domain of the i-th column of R and the domain of the i-th column of S must be the same   
   
#### Cartesian product operation   
// 카티시언 프로덕트 연산   
   
// 두 릴레이션에 포함된 레코드 간의 모든 조합을 생성하는 이항 연산자   
- A binary operator that generates all combinations of records in both relations   
  - R × S   
    - R : a<sub>record</sub> × m<sub>column</sub>   
    - S : b<sub>record</sub> × n<sub>column</sub>   
    - R × S : (a × b)<sub>record</sub> × (m + n)<sub>column</sub>   
   
#### Join Operation   
// 조인 연산   
   
// 두 릴레이션에서 조건을 만족하는 레코드를 결합한 레코드로 구성된 릴레이션을 생성   
- Create a relationship consisting of records that combine records that meet the conditions in both relationships   
  - R ⋈ <sub>A ⊝ B</sub> S   
    - σ <sub>A ⊝ B</sub> (R × S)   
   
#### Examples of Join Operation   
// 조인 연산의 예시   
   
- Professor Relation   
   
|Professor number|Professor name|Position|Department of affiliation|Annual salary|
|:---:|:---:|:---:|:---|---:|
|100-0001|Choi|Professor|Life Science|80,000,000|
|200-0002|Han|Associate Professor|Life Science|60,000,000|
|300-0003|Park|Assistant Professor|Life Science|40,000,000|
|100-0004|Kim|Professor|Computer Science|80,000,000|
|300-0005|Jung|Assistant Professor|Computer Science|40,000,000|
|100-0006|Lee|Professor|Law|80,000,000|
|100-0007|Hwang|Professor|Public Administration|80,000,000|
   
- Subject Relation   
   
|Subject code|Subject name|Credit|Professor number|
|:---|:---|:---|:---|
|001|Life Science Theory|3|100-0001|
|002|Introduction to Life Science|3|200-0002|
|003|Life science Practice|3|300-0003|
|004|Introduction to Computer|3|100-0004|
|005|Computer Basic Practice|3|300-0005|
|006|Concept of Law|3|100-0006|
|007|Administrative Foundations|3|100-0007|
   
- Professor Relation ⋈ <sub>Professor Relation.Professor number = Subject Relation.Professor number</sub> Subject Relation   
  - σ <sub>Professor Relation.Professor number = Subject Relation.Professor number</sub> (Professor Relation × Subject Relation)   
   
|Professor number|Professor name|Position|Department of affiliation|Annual salary|Subject code|Subject name|Credit|Professor number|
|:---:|:---:|:---:|:---|---:|:---|:---|:---|:---|
|100-0001|Choi|Professor|Life Science|80,000,000|001|Life Science Theory|3|100-0001|
|200-0002|Han|Associate Professor|Life Science|60,000,000|002|Introduction to Life Science|3|200-0002|
|300-0003|Park|Assistant Professor|Life Science|40,000,000|003|Life science Practice|3|300-0003|
|100-0004|Kim|Professor|Computer Science|80,000,000|004|Introduction to Computer|3|100-0004|
|300-0005|Jung|Assistant Professor|Computer Science|40,000,000|005|Computer Basic Practice|3|300-0005|
|100-0006|Lee|Professor|Law|80,000,000|006|Concept of Law|3|100-0006|
|100-0007|Hwang|Professor|Public Administration|80,000,000|007|Administrative Foundations|3|100-0007|
   
#### Aggregation Function operation 1   
// 집계 함수 연산 1   
   
// 집계 함수를 값들의 집합 또는 레코드의 집합에 적용하는 연산   
- The operation of applying an Aggregate Function to a set of values or a set of records   
  - ℊ<sub>x(A)</sub>(R)   
    - <sub>x()</sub> : Aggregate Functions such as AVG, SUM, MIN, MAX, COUNT, etc.   
    - <sub>A</sub> : Column to apply aggregate operations to    - (R) : Relation   
   
#### Examples of Aggregation Function 1   
// 집계 함수의 예시 1   
   
- Subject Relation   
   
|Subject code|Subject name|Credit|Professor number|
|:---|:---|:---|:---|
|001|Life Science Theory|3|100-0001|
|002|Introduction to Life Science|3|200-0002|
|003|Life science Practice|3|300-0003|
|004|Introduction to Computer|3|100-0004|
|005|Computer Basic Practice|3|300-0005|
|006|Concept of Law|3|100-0006|
|007|Administrative Foundations|3|100-0007|
   
- ℊ<sub>count(Subject name)</sub>(Subject Relation)   
   
|count(Subject name)|
|:---:|
|7|
   
#### Aggregation Function operation 2   
// 집계 함수 연산 2   
   
// 레코드 그룹화를 위해 집계 함수 연산자 앞에 그룹화 속성을 기술   
- Describes grouping properties before aggregation function operators for record grouping   
  - <sub>B</sub>ℊ<sub>x(A)</sub>(R)   
    - <sub>B</sub> : The column that serves as the basis for the group   
    - <sub>x()</sub> : Aggregate Functions such as AVG, SUM, MIN, MAX, COUNT, etc.   
    - <sub>A</sub> : Column to apply aggregate operations to   
    - (R) : Relation   
   
#### Examples of Aggregation Function 2   
// 집계 함수의 예시 2   
   
- Professor Relation   
      
|Professor number|Professor name|Position|Department of affiliation|Annual salary|
|:---:|:---:|:---:|:---|---:|
|100-0001|Choi|Professor|Life Science|80,000,000|
|200-0002|Han|Associate Professor|Life Science|60,000,000|
|300-0003|Park|Assistant Professor|Life Science|40,000,000|
|100-0004|Kim|Professor|Computer Science|80,000,000|
|300-0005|Jung|Assistant Professor|Computer Science|40,000,000|
|100-0006|Lee|Professor|Law|80,000,000|
|100-0007|Hwang|Professor|Public Administration|80,000,000|
   
- <sub>Department of affiliation</sub>ℊ<sub>Department of affiliation, count(*)</sub>(Professor Relation)   
   
|Department of affiliation|count(*)|
|:---:|:---:|
|Life Science|3|
|Computer Science|2|
|Law|1|
|Public Administration|1|
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
