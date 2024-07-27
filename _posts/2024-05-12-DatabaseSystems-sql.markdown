---
layout: post
title:  "Database Systems: SQL"
date:   2024-05-12 09:00:00 +0900
categories: [Database Systems]
---

### Overview of SQL (Structured Query Language)   
// SQL (Structured Query Language) 의 개요   
   
// 관계 대수에 기초하여 RDBMS의 데이터 관리를 위해 설계된 언어   
// 1986년 ANSI, 1987년 ISO에서 표준으로 제정   
// - SQL-86, SQL-89, SQL-92, SQL:1999, SQL:2003, SQL:2008   
// - 상용 DBMS의 특성에 맞게 국제표준을 확장한 독자적 버전이 존재   
// 특징   
// - 비절차적 (선언형) 언어, 필요한 데이터만 기술   
// - 인간의 언어와 매우 유사하고 간단, 명료함   
- Language designed for data management in RDBMS based on relational algebra   
- It was established as a standard by ANSI in 1986 and ISO in 1987   
  - SQL-86, SQL-89, SQL-92, SQL:1999, SQL:2003, SQL:2008   
  - There is an independent version that extends the international standards to suit the characteristics of commercial DBMS   
- Characteristics   
  - Non-procedural (declarative) language. Describes only the necessary data   
  - It is very similar to human language, simple, and clear   
   
<br />
### Configure of SQL   
// SQL의 구성   
   
// 데이터 정의 언어   
// - 데이터베이스 내의 객체를 생성 및 삭제하고 그 구조를 조작하는 명령어의 집합   
// - 데이터가 준수해야 하는 제약조건을 기술   
// - CREATE, ALTER, DROP 문 등   
- DDL (Data Definition Language)   
  - A set of commands that create and delete objects in the database and manipulate their structures   
  - Describe the constraints that the data must comply with   
  - CREATE, ALTER, DROP statement, etc.   
   
// 데이터 조작 언어   
// - DDL에 의해 정의된 테이블에 데이터를 조작하는 명령어의 집합   
// - 데이터에 대한 CRUD (생성, 검색, 삭제, 수정) 명령을 포함   
// - INSERT, UPDATE, DELETE, SELECT 문 등   
- DML (Data Manipulation Language)   
  - Set of commands to manipulate data in a table defined by DDL   
  - Include CRUD (create, search, delete, update) commands for data   
  - INSERT, UPDATE, DELETE, SELECT statement, etc.   
   
// 데이터 제어 언어   
// - 데이터베이스에 접근하고 객체들을 사용하도록 권한을 주고 회수하는 명령어의 집합   
// - GRANT, REVOKE 문 등   
- DCL (Data Control Language)   
  - A set of commands that authorize and search the database to access and use the objects   
  - GRANT, REVOKE statement, etc.   
   
<br />
### DDL (Data Definition Language)   
// 데이터 정의 언어   
   
#### Concept of Data Definition Language   
// 데이터 정의 언어의 개념   
   
// 데이터베이스 객체를 생성, 삭제 또는 구조를 수정하는 명령어의 집합   
- A set of instructions that create, delete objects in the database, or  modify the structure of the database   
   
// 데이터베이스 객체의 종류   
// - 데이터 저장 : 테이블, 인덱스, 뷰   
// - 데이터 조작 : 트리거, 프로시저, 함수 등   
- Types of database objects   
  - Storage of data : table, indexe, view   
  - Data manipulation : triggers, procedures, functions, etc.   
   
// 데이터 정의 명령어의 종류   
// - CREATE : 객체 생성   
// - ALTER : 객체 수정   
// - DROP : 객체 삭제   
- Types of data definition commands   
  - CREATE : Create Object   
  - ALTER : Modify Object   
  - DROP : Delete Object   
   
#### Schema Definition   
// 스키마 정의   
   
// 스키마 = 데이터베이스   
// 한 조직의 데이터베이스 시스템의 운영에 필요한 테이블, 인덱스, 뷰 등의 데이터베이스 객체의 집합   
- Schema = Database   
- A set of database objects, such as tables, indexes, views, etc., that are required to operate a database system in an organization   
   
// 스키마 관리 방법   
// - Forward Engineer   
// - SQL 에디터   
// - 내비게이터 패널   
- How to Manage Schemas   
  - Forward Engineer   
  - SQL Editor   
  - Navigator Panel   
   
// 스키마 관리 구문 형식   
// - 스키마 생성 : `CREATE SCHEMA 스키마 이름`   
// - 스키마 삭제 : `DROP SCHEMA 스키마 이름`   
- Syntax format of schema Management   
  - Create schema : `CREATE SCHEMA schemaName`   
  - Delete schema : `DROP SCHEMA schemaName`   
   
#### Table definition   
// 테이블 정의   
   
// 새로운 2차원 형태의 테이블을 생성   
- Create a new two-dimensional table   
   
// 구문 형식   
- Syntax format   
   
```sql
/*
CREATE TABLE 테이블이름(
    <컬럼1> <데이터타입1> [제약조건1][,
    <컬럼2> <데이터타입2> [제약조건2]]
    ... [,
    <컬럼n> <데이터타입N> [제약조건N]]
    [PRIMARY KEY 컬럼명]
    [UNIQUE 컬럼명]
    [FOREIGN KEY 컬럼 REFERENCES 테이블이름(컬럼)]
)
*/
CREATE TABLE tableName(
    <column1> <dataType1> [constraints1][,
    <column2> <dataType2> [constraints2]]
    ... [,
    <columnN> <dataTypeN> [constraintsN]]
    [PRIMARY KEY columnName]
    [UNIQUE columnName]
    [FOREIGN KEY column REFERENCES tableName(column)]
)
```
   
#### Example of table creation   
// 테이블 생성 예시   
   
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
   
- SQL   
   
```sql
/*
CREATE TABLE 교수(
    교수번호 CHAR(13) NOT NULL,
    교수이름 CHAR(30) NOT NULL,
    직위 CHAR(10) NOT NULL,
    소속학과 CHAR(50) NOT NULL,
    연봉 INT NOT NULL)
*/
CREATE TABLE professor(
    professorNumber CHAR(13) NOT NULL,
    professorName CHAR(30) NOT NULL,
    position CHAR(10) NOT NULL,
    affiliatedDepartment CHAR(50) NOT NULL,
    annualSalary INT NOT NULL)
```
   
#### Concept of Data Type   
// 데이터 타입의 개념   
   
// 컬럼이 가질 수 있는 값의 범위, 즉 도메인을 결정   
// 프로그래밍 언어에서의 변수를 생성하는 데이터 타입의 사용목적과 방법이 매우 유사   
// 기본 데이터 타입   
// - 문자 : CHAR(n), VARCHAR(n), TEXT   
// - 숫자 : INT, FLOAT, DOUBLE, DECIMAL(m, n)   
// - 날짜 / 시간 : DATE, TIME, DATETIME, TIMESTAMP   
- Determine the range of values a column can have, i.e., the domain   
- The purpose and method of using data types that generate variables in programming languages are very similar   
- Default data type   
  - Character : CHAR(n), VARCHAR(n), TEXT   
  - Number : INT, FLOAT, DOUBLE, DECIMAL(m, n)   
  - Date / Time : DATE, TIME, DATETIME, TIMESTAMP   
   
// 정수 데이터 타입   
// - TINYINT   
// -- 1바이트 정수   
// -- -128 ~ 127   
// -- 나이, 학년 등의 크기가 작은 정수   
// - SMALLINT   
// -- 2바이트 정수   
// -- -32768 ~ 32767   
// -- 물품번호, 인원 등 중간 크기의 정수   
// - INT   
// -- 4바이트 정수   
// -- 약 -20억 ~ 20억   
// -- 물품의 금액, 전화번호 등의 일반 크기의 정수   
// - BIGINT   
// -- 8바이트 정수   
// -- 계좌의 잔고, 천문학적인 크기의 정수   
- Integer data type   
  - TINYINT   
    - 1-byte integer   
    - -128 ~ 127   
    - Small-sized integers of age, grade, etc.   
  - SMALLINT   
    - 2-byte integer   
    - -32768 ~ 32767   
    - Medium-sized integers such as item number, number of people, etc.   
  - INT   
    - 4-byte integer   
    - About -2 billion to 2 billion   
    - An integer of a normal size, such as the amount of goods, phone number, etc.   
  - BIGINT   
    - 8-byte integer   
    - An integer such as the balance of an account, astronomical size, etc.   
   
// 실수 데이터 타입   
// - 고정 소수형   
// -- DECIMAL(M, N) : 전체 M 자리, 소수점 이하 N 자리의 숫자   
// --- 예시 : DECIMAL(5, 2) 는 -999.99 ~ 999.99   
// -- NUMERIC - DECIMAL과 동일   
// - 부동 소수형   
// -- FLOAT : 4바이트 크기 부동 소수   
// -- FLOAT(P) : 소수점 이하 P개 자리의 부동 소수   
// -- DOUBLE : 8바이트 크기 부동 소수   
- Real number data type   
  - Fixed prime number type   
    - DECIMAL(M, N) : All M digits, N decimal number   
      - Example : DECIMAL(5, 2) is -999.99 ~ 999.99   
    - NUMERIC - Same as DECIMAL   
  - Floating prime number type   
    - FLOAT : 4-byte floating prime number   
    - FLOAT(P) : Floating prime numbers with P decimal places   
    - DOUBLE : 8-byte floating prime number   
   
// 날짜 데이터 타입   
// - DATE : `YYYY-MM-DD` 형식의 시간   
// - YEAR : `YYYY` 형식의 연도   
- Date data type   
  - DATE : Time in the format of `YYYY-MM-DD`   
  - YEAR : Year in the format of `YYYY`   
   
// 시간 데이터 타입   
// - TIME : `HH:MI:SS` 형식의 시간   
- Time data type   
  - TIME : Time in the format of `HH:MI:SS`   
   
// 날짜 및 시간 데이터 타입   
// - DATETIME : `YYYY-MM-DD HH:MI:SS` 형식의 날짜 및 시간   
// - TIMESTAMP : DATETIME과 동일   
- Date and time data types   
  - DATETIME : Date and time in the format of `YYYY-MM-DD HH:MI:SS`   
  - TIMESTAMP : Same as DATETIME   
   
// 문자 데이터 타입   
// - CHAR(N) : 최대 길이가 N인 고정길이 문자열   
// - VARCHAR(N) : 최대 길이가 N인 가변길이 문자열   
// - TEXT, CLOB : 길이가 최대 2 ~ 4 GB 인 가변길이 문자열   
// - ENUM : 유한개의 문자열 집합 중 하나의 값을 선택   
// -- 성별 : ENUM('남', '여')   
// -- 혈액형 : ENUM('A', 'B', 'O', 'AB')   
- Character data type   
  - CHAR(N) : Fixed length string with maximum length N   
  - VARCHAR(N) : Variable length string with maximum length N   
  - TEXT, CLOB : Variable length string up to 2 to 4 GB in length   
  - ENUM : Select one value from a finite set of strings   
    - Gender : ENUM ('Male', 'Female')   
    - Blood type : ENUM('A', 'B', 'O', 'AB')   
   
// 문자열 저장 예시   
// - `DATABASE` 문자열 저장 시   
// -- CHAR(10) 으로 저장 시 `DATABASE널널`   
// -- VARCHAR(10) 으로 저장 시 `DATABASE`   
- Example of string storage   
  - When saving the string `DATABASE`   
    - When stored as CHAR(10), `DATABASEhasSpace`   
    - When stored as VARCHAR(10), `DATABASE`   
   
#### Updating the table   
// 테이블 수정   
   
// 생성된 테이블에 컬럼을 추가, 수정 (이름, 데이터 타입, 제약조건) 또는 삭제하는 명령   
// 컬럼 삭제 또는 컬럼의 데이터 타입 수정 시 데이터에 대한 소실이 발생하므로 많은 주의가 요구됨   
// 테이블 수정 방법   
// - SQL 구문   
// - 내비게이터 패널   
- Commands to add, modify (name, data type, constraint), or delete columns in crated tables   
- Data loss occurs when deleting columns or modifying the data type of columns, which requires a lot of attention   
- To modify a table   
  - SQL syntax   
  - Navigator panel   
   
#### Syntax format of updating the table   
// 테이블 수정 구문 형식   
   
```sql
/*
// 컬럼 추가
ALTER TABLE 테이블이름
    [ADD COLUMN 컬럼 데이터타입 [제약조건]]
// 컬럼 삭제
ALTER TABLE 테이블이름
    [DROP COLUMN 컬럼이름]
// 컬럼 이름 변경
ALTER TABLE 테이블이름
    [CHANGE COLUMN 수정전컬럼이름 수정후컬럼이름]
// 컬럼 데이터타입 변경
ALTER TABLE 테이블이름
    [MODIFY COLUMN 컬럼 데이터타입]
*/
/* Add column */
ALTER TABLE tableName
    [ADD COLUMN column dataType [constraints]]
/* Delete column */
ALTER TABLE tableName
    [DROP COLUMN columnName]
/* Change column name */
ALTER TABLE tableName
    [CHANGE COLUMN columnNameBeforeModification columnNameAfterModification]
/* Change column data type */
ALTER TABLE tableName
    [MODIFY COLUMN column dataType]
```
   
#### Example of table modification query   
// 테이블 수정 질의 예시   
   
// 교수 테이블에 데이터 타입이 INT인 나이 컬럼을 추가하시오   
- Add an age column of data type INT to the professor table   
   
```sql
/*
ALTER TABLE 교수
    ADD COLUMN 나이 INT
*/
ALTER TABLE professor
    ADD COLUMN age INT
```
   
#### Delete the table   
// 테이블 삭제   
   
// 존재하는 테이블을 스키마에서 삭제   
// 삭제할 테이블의 모든 데이터가 소실되고, 복구가 불가능한 연산이므로 각별한 주의가 요구됨   
- Delete existing tables from schema   
- All data in the table to be deleted is lost, and special attention is required because it is an operation that cannot be recovered   
   
// 테이블 삭제 방법   
// - SQL 구문   
// - 내비게이터 패널   
- How to delete a table   
  - SQL syntax   
  - Navigator panel   
   
#### Syntax format of delete the table   
// 테이블 삭제 구문 형식   
   
```sql
/*
DROP TABLE 테이블이름
*/
DROP TABLE tableName
```
   
#### Constraints   
// 제약조건   
   
// 테이블과 테이블에 존재하는 데이터를 보다 무결하게 관리하기 위한 목적으로 사용   
// DBMS는 테이블 조작 시 테이블에 정의된 제약조건을 만족시키는지 지속적으로 검사함   
// DBMS는 적용하려는 제약의 유형에 따라 다양한 제약조건을 지원함   
- Used for more flawless management of tables and their data   
- DBMS continuously inspects the table to meet the constraints defined in the table when operating the table   
- DBMS supports various constraints depending on the type of constraints you want to apply   
   
// 제약조건의 종류   
// - PRIMARY KEY : 기본키 지정, UNIQUE 와 NOT NULL 특성   
// - FOREIGN KEY : 외래키 지정, 참조 컬럼 정의   
// - NOT NULL : NULL이 될 수 없는 컬럼에 지정   
// - UNIQUE : 동일한 컬럼값을 가질 수 없음을 지정   
// - AUTO_INCREMENT : 레코드가 추가될 때 자동적으로 속성값이 1부터 1씩 증가되어 입력   
// - CHECK : 컬럼값이 특정 조건 준수 여부 지정   
- Types of constraints   
  - PRIMARY KEY : Specify default keys, Characteristics of UNIQUE and NOT NULL   
  - FOREIGN KEY : Specify Foreign Key, Reference Column Definition   
  - NOT NULL : Specify a column that cannot be NULL   
  - UNIQUE : Specify that column values cannot be the same   
  - AUTO_INCREMENT : The property value starts at 1, and is automatically increased by the number 1 when the record is added   
  - CHECK : Specify whether column values comply with certain conditions   
   
#### Use of Constraints   
// 제약조건의 사용   
   
- Professor Relation   
   
|Professor number (PK)|Professor name|Position|Department of affiliation (FK)|Annual salary|
|:---:|:---:|:---:|:---|---:|
|100-0001|Choi|Professor|Life Science|80,000,000|
|200-0002|Han|Associate Professor|Life Science|60,000,000|
|300-0003|Park|Assistant Professor|Life Science|40,000,000|
|100-0004|Kim|Professor|Computer Science|80,000,000|
|300-0005|Jung|Assistant Professor|Computer Science|40,000,000|
|100-0006|Lee|Professor|Law|80,000,000|
|100-0007|Hwang|Professor|Public Administration|80,000,000|
   
- SQL   
   
```sql
/*
CREATE TABLE 교수(
    교수번호 CHAR(13) NOT NULL,
    교수이름 CHAR(30) NOT NULL,
    직위 CHAR(10) NOT NULL,
    소속학과 CHAR(50) NOT NULL,
    연봉 INT NOT NULL
    PRIMARY KEY(교수번호),
    FOREIGN KEY(소속학과) REFERENCES 학과(학과이름)
)
*/
CREATE TABLE professor(
    professorNumber CHAR(13) NOT NULL,
    professorName CHAR(30) NOT NULL,
    position CHAR(10) NOT NULL,
    affiliatedDepartment CHAR(50) NOT NULL,
    annualSalary INT NOT NULL
    PRIMARY KEY(professorNumber),
    FOREIGN KEY(affiliatedDepartment) REFERENCES department(departmentName)
)
```
   
<br />
### DML (Data Manipulation Language)   
// 데이터 조작 언어   
   
#### Concept of data manipulation language   
// 데이터 조작 언어의 개념   
   
// 정의된 테이블에 레코드에 삽입, 수정, 삭제 및 검색하는데 사용되는 명령어의 집합   
- A set of commands used to insert, modify, delete, and search records in a defined table   
   
// 명령어의 종류   
// - INSERT : 테이블 스키마에 적합한 레코드를 삽입   
// - UPDATE : 테이블에서 조건을 만족하는 특정 레코드의 컬럼값을 수정   
// - DELETE : 테이블에 조건을 만족하는 특정 레코드를 삭제   
// - SELECT : 조건을 만족하는 레코드를 테이블에서 검색   
- Types of commands   
  - INSERT : Insert the appropriate record for the table schema   
  - UPDATE : Modifying the column value of a particular record that meets the condition in the table   
  - DELETE : Delete certain records that meet the conditions in the table   
  - SELECT : Search the table for records that meet the criteria   
   
#### INSERT   
// 데이터 삽입   
   
// 테이블에 새로운 레코드를 삽입하는 명령문   
// - 테이블에 새로운 레코드를 삽입   
// - 모든 속성 또는 부분 속성에 대한 속성값을 삽입   
- Command statement to insert a new record into the table   
  - Insert a new record into the table   
  - Insert property values for all properties or partial properties   
   
#### Syntax format of insert the data   
// 데이터 삽입 구문 형식   
   
```sql
/*
INSERT INTO 테이블이름
    VALUES(값1, 값2, ..., 값N)
*/
INSERT INTO tableName
    VALUES(value1, value2, ..., valueN)
```
   
```sql
/*
INSERT INTO 테이블이름(컬럼1, 컬럼2, ..., 컬럼N)
    VALUES(값1, 값2, ..., 값N)
*/
INSERT INTO tableName(column1, column2, ..., columnN)
    VALUES(value1, value2, ..., valueN)
```
   
#### Example 1 of data insert   
// 데이터 삽입 예시 1   
   
// 학과이름 '영어영문학과', 단과대학 '인문과학대학', 주소 'http://abc.ac.kr', 전화번호 'O1O-OOOO-OOOO', 졸업학점 135 인 레코드를 학과 테이블에 삽입하시오   
- Insert a record with department name 'English Literature Department', college of 'Humanities and Sciences Department', address 'http://abc.ac.kr', phone number 'O1O-OOOO-OOOO', and 135 graduation credits into the department table   
   
```sql
/*
INSERT INTO 학과
    VALUES('영어영문학과', '인문과학대학', 'http://abc.ac.kr', 'O1O-OOOO-OOOO', 135)
*/
INSERT INTO department
    VALUES('English Literature Department', 'Humanities and Sciences Department', 'http://abc.ac.kr', 'O1O-OOOO-OOOO', 135)
```
   
#### Example 2 of data insert   
// 데이터 삽입 예시 2   
   
// 단과대학 '자연과학대학', 학과이름 '농학과', 졸업학점 140, 전화번호 'O1O-OOOO-OOOO' 인 레코드를 학과 테이블에 삽입하시오   
- Insert a record with college of 'Natural sciences', department name 'Agriculture Department', 140 graduation credits, and phone number 'O1O-OOOO-OOOO' into the department table   
   
```sql
/*
INSERT INTO 학과(단과대학, 학과이름, 졸업학점, 전화번호)
    VALUES('자연과학대학', '농학과', 140, 'O1O-OOOO-OOOO')
*/
INSERT INTO department(college, departmentName, graduationCredits, phoneNumber)
    VALUES('Natural sciences', 'Agriculture Department', 140, 'O1O-OOOO-OOOO')
```
   
#### UPDATE   
// 데이터 수정   
   
// 조건을 만족하는 레코드의 특정 컬럼값을 수정   
- Modifying a specific column value for a record that satisfies the condition   
   
#### Syntax format of updating the table   
// 데이터 수정 구문 형식   
   
```sql
/*
UPDATE 테이블이름
    SET 컬럼1 = 값1[, 컬럼2 = 값2, ..., 컬럼N = 값N]
    [WHERE 조건]
*/
UPDATE tableName
    SET column1 = value1[, column2 = value2, ..., columnN = valueN]
    [WHERE condition]
```
   
```sql
/*UPDATE 테이블이름
    SET 컬럼1 = 수식1[, 컬럼2 = 수식2, ..., 컬럼N = 수식N]
    [WHERE 조건]
*/
UPDATE tableName
    SET column1 = expression1[, column2 = expression2, ..., columnN = expressionN]
    [WHERE condition]
```
   
#### Example 1 of data modify   
// 데이터 수정 예시 1   
   
// 학과이름이 '농학과' 인 레코드의 주소 컬럼값을 'http://abc.ac.kr' 로 수정하시오   
- Modify the address column value of the record whose department name is 'Agriculture Department' to 'http://abc.ac.kr'   
   
```sql
/*
UPDATE 학과
    SET 주소 = 'http://abc.ac.kr'
    WHERE 학과이름 = '농학과'
*/
UPDATE department
    SET address = 'http://abc.ac.kr'
    WHERE departmentName = 'Agriculture Department'
```
   
#### Example 2 of data modify   
// 데이터 수정 예시 2   
   
// 잔액이 500,000원 이상인 학생 계좌에 2% 이자를 지급하시오   
- Pay 2% interest to a student account with a balance of 500,000 won or more   
   
```sql
/*
UPDATE 학과
    SET 잔액 = 잔액 * 1.02
    WHERE 잔액 >= 500000
*/
UPDATE department
    SET balance = balance * 1.02
    WHERE balance >= 500000
```
   
#### DELETE   
// 데이터 삭제   
   
// 조건에 일치하는 레코드 집합을 테이블에서 삭제할 때 사용하는 명령어   
- Commands used to delete a set of records that match a condition from the table   
   
#### Syntax format of delete the table   
// 데이터 삭제 구문 형식   
   
```sql
/*
DELETE FROM 테이블이름
    [WHERE 조건]
*/
DELETE FROM tableName
    [WHERE condition]
```
   
#### Example 1 of data delete   
// 데이터 삭제 예시 1   
   
// 소속학과가 '행정학과'인 교수의 레코드를 삭제하시오   
- Delete the professor's record, whose department is the 'Department of Public Administration'   
   
```sql
/*
DELETE FROM 교수
    WHERE 소속학과 = '행정학과'
*/
DELETE FROM professor
    WHERE affiliatedDepartment = 'Department of Public Administration'
```
   
#### Example 2 of data delete   
// 데이터 삭제 예시 2   
   
// 모든 강의 레코드를 삭제하시오   
- Delete all lecture records   
   
```sql
/*
DELETE FROM 과목
*/
DELETE FROM subject
```
   
#### SAFE UPDATES Mode   
// SAFE UPDATES 모드   
   
// WHERE 절이 없는 UPDATE / DELETE 문은 테이블의 전체 레코드를 변경 / 삭제할 수 있음   
// 의도하지 않은 데이터 변경 / 삭제 방지를 위해 MySQL은 SAFE UPDATES 모드를 지원   
// 기본키가 아닌 컬럼을 대상으로 수정 / 삭제 조건을 명시할 경우 실행 여부를 결정   
- A UPDATE / DELETE statement without a WHERE clause can change / delete the entire record in the table   
- To prevent unintended data changes / deletion, MySQL supports SAFE UPDATES mode   
- Decide whether to execute when specifying update / deletion conditions for non-default columns   
   
#### Syntax format of SAFE UPDATES   
// SAFE UPDATES 구문 형식   
   
```sql
/*
SET SQL_SAFT_UPDATES = 0 또는 1
*/
SET SQL_SAFT_UPDATES = 0 or 1
```
   
<br />
### SELECT   
// 데이터 검색   
   
// 한 개 이상의 테이블에서 주어진 조건에 만족하는 레코드를 출력하는 명령문   
// 관계 대수의 셀렉션, 프로젝션, 조인, 카티션 프로덕트 연산자의 기능을 모두 포함하고 있는 명령문   
// 필수적 절인 SELECT 절과 부가적인 목적으로 사용할 수 있는 여러 절을 혼합하여 검색 기능을 구체화   
- Command statement that outputs records that satisfy a given condition in one or more tables   
- Command statements that contain all the functions of the selection, projection, join, and cartesian product operators of relational algebra   
- It embodies search capabilities by mixing essential clause SELECT clause with several clauses that can be used for additional purposes   
   
#### Syntax format of SELECT clause   
// SELECT 문 구문 형식   
   
```sql
/*
SELECT [DISTICT] 컬럼1, 컬럼2, ..., 컬럼n
    FROM 테이블1 [INNER JOIN | OUTER JOIN
         테이블2 INNER JOIN | OUTER JOIN
         ON 조인조건1
         테이블3
         ..., INNER JOIN | OUTER JOIN
         테이블M]
    [ON 조인조건식]
    [WHERE 조건식 [중첩 질의]]
    [GROUP BY 컬럼1, 컬럼2, ..., 컬럼y]
        [HAVING 조건]
    [ORDER BY 컬럼1 [ASC|DESC], ..., 컬럼z [ASC|DESC]]
*/
SELECT [DISTICT] column1, column2, ..., columnN
    FROM table1 [INNER JOIN | OUTER JOIN
         table2 INNER JOIN | OUTER JOIN
         ON joinCondition1
         table3
         ..., INNER JOIN | OUTER JOIN
         tableM]
    [ON JoinConditionExpression]
    [WHERE conditionExpression [NestingQuery]]
    [GROUP BY column1, column2, ..., columnY]
        [HAVING condition]
    [ORDER BY column1 [ASC|DESC], ..., columnZ [ASC|DESC]]
```
   
#### Features of each clause of the SELECT statement   
// SELECT 문의 각 절의 기능   
   
// SELECT 절 : 결과에 포함되는 컬럼을 지정   
// FROM 절 : 질의를 적용할 테이블을 지정   
// ON / WHERE 절 : 조인조건 / 검색할 레코드 조건을 지정   
// GROUP BY 절 : 레코드를 그룹화하기 위한 그룹 조건을 지정   
// HAVING 절 : GROUP BY 절이 적용된 결과에 대한 조건을 지정   
// ORDER BY 절 : 검색 결과의 정렬 기준을 지정   
- SELECT clause : Specify columns to be included in the results   
- FROM clause : Specify the table to which the query will be applied   
- ON / WHERE clause : Join condition / specify the conditions for records to be searched   
- GROUP BY clause : Specify group conditions for grouping records   
- HAVING clause : Specify conditions for results with the GROUP BY clause applied   
- ORDER BY clause : Specify sorting criteria for search results   
   
#### Simple Query   
// 단순질의문   
   
// 레코드를 제한하지 않고 전체 테이블을 검색하는 SELECT 문으로 WHERE 절이 없는 질의문   
- A SELECT statement that searches the entire table without limiting records, without a WHERE clause   
   
#### Syntax format of simple query   
// 단순질의문 구문 형식   
   
```sql
/*
SELECT 컬럼1, 컬럼2, ..., 컬럼N
    FROM 테이블
*/
SELECT column1, column2, ..., columnN
    FROM table
```
   
```sql
/*
SELECT *
    FROM 테이블
*/
SELECT *
    FROM table
```
   
// 중복값은 한번만 출력하려면 DISTINCT 사용   
- Use DISTINCT to output duplicate values only once   
   
```sql
/*
SELECT DISTINCT *
    FROM 테이블
*/
SELECT DISTINCT *
    FROM table
```
   
#### Example of simple query   
// 단순질의문 예시   
   
// 교수 테이블에서 '소속학과' 컬럼을 선택하여 출력하시오   
- Select and print the 'affiliated department' column from the professor table   
   
```sql
/*
SELECT 소속학과
    FROM 교수
*/
SELECT affiliatedDepartment
    FROM professor
```
   
// 중복값은 한번만 출력   
- Output duplicate values only once   
   
```sql
/*
SELECT DISTINCT 소속학과
    FROM 교수
*/
SELECT DISTINCT affiliatedDepartment
    FROM professor
```
   
#### Conditional Query   
// 조건질의문   
   
// 산술 연산식, 함수 등을 사용하여 표현한 조건을 WHERE 절에 기술하여 조건을 만족하는 레코드만 검색하는 SELECT 문   
// - 산술 연산자   
// - 비교 연산자   
// - 논리 연산자   
- The conditions expressed using arithmetic expressions, functions, etc., are described in the WHERE clause, and the SELECT statement searching only for records that satisfy the conditions   
  - Arithmetic operator   
  - Comparison operator   
  - Logical operator   
   
// WHERE 절은 UPDATE, DELETE 문에서도 동일하게 적용   
- The WHERE clause applies equally to UPDATE and DELETE statements   
   
#### Arithmetic operator   
// 산술 연산자   
   
// SELECT 절 또는 WHERE 절에 사용되어 컬럼값 또는 상수와의 산술 계산을 위한 연산자   
- Operators used in SELECT or WHERE clauses for arithmetic calculations with column values or constants   
   
|Type|Use Example|Meaning|
|:---:|:---|:---|
|DIV|// 컬럼명 DIV 상수(또는 컬럼명)<br />- Column Name DIV Constant (or column name)|// 정수 나눗셈<br />- Integer division|
|/|// 컬럼명 / 상수(또는 컬럼명)<br />- Column Name / Constant (or column name)|// 나눗셈 연산자<br />- Division operator|
|-|// 컬럼명 - 상수(또는 컬럼명)<br />- Column Name - Constant (or column name)|// 뺄셈 연산자<br />- Subtraction operator|
|%, MOD|// 컬럼명 % 상수(또는 컬럼명)<br />- Column Name % Constant (or column name)|// 나머지 연산자<br />- Remaining operator|
|+|// 컬럼명 + 상수(또는 컬럼명)<br />- Column Name + Constant (or column name)|// 덧셈 연산자<br />- Addition operator|
|*|// 컬러명 * 상수(또는 컬럼명)<br />- Column Name * Constant (or column name)|// 곱셈 연산자<br />- Multiplication operator|
   
#### Comparison operator   
// 비교 연산자   
   
// 컬럼값과 상수 또는 컬럼값과 다른 컬럼값과의 크기를 비교하는 연산자   
- Operator to compare the size of a column value with a constant, or to compare the size of a column value with another column value   
   
|Type|Use Example|Meaning|
|:---:|:---|:---|
|=|// 컬럼_이름 = X<br />- Column_Name = X|// 컬럼값이 X와 같은<br />- Column value equal to X|
|＜|// 컬럼_이름 ＜ X<br />- Column_Name ＜ X|// 컬럼값이 X보다 작은<br />- Column value less than X|
|＜=|// 컬럼_이름 ＜= X<br />- Column_Name ＜= X|// 컬럼값이 X보다 작거나 같은<br />- Column value less than or equal to X|
|＞|// 컬럼_이름 ＞ X<br />- Column_Name ＞ X|// 컬럼값이 X보다 큰<br />- Column value greater than X|
|＞=|// 컬럼_이름 ＞= X<br />- Column_Name ＞= X|// 컬럼값이 X보다 크거나 같은<br />- Column value greater than or equal to X|
|!= or ＜＞|// 컬럼_이름 ＜＞ X<br />- Column_Name ＜＞ X|// 컬럼값이 X와 같지 않은<br />- column value not equal to X|
   
#### Logical operator   
// 논리 연산자   
   
// 두 개 이상의 조건이 기술된 질의문에서 조건식 간의 관계를 정의하는 연산자   
- An operator that defines the relation between conditional expressions in a query with two or more conditions described   
   
|Type|Use Example|Meaning|
|:---:|:---|:---|
|AND or &&|// 조건1 AND 조건2<br />- Condition1 AND condition2|// 조건1과 조건2를 동시에 만족하는<br />- Satisfying conditions 1 and 2 at the same time|
|OR or \|\||// 조건1 OR 조건2<br />- Condition1 OR condition2|// 조건1과 조건2를 적어도 하나 만족하는<br />- At least one of the conditions 1 and 2 is satisfied|
|NOT or !|// NOT 조건1<br />- NOT condition1|// 조건1이 참이 아닌<br />- Condition 1 is not true|
   
#### Example 1 of conditional query   
// 조건질의문 예시 1   
   
// 이수구분 '전공필수'인 과목의 과목명, 학점, 선수과목을 출력하시오   
- Please print out the subject name, credit, and pre-subject of the course in which the completion classification is 'Major Required'   
   
```sql
/*
SELECT 과목명, 학점, 선수과목 FROM 과목
    WHERE 이수구분 = '전공필수'
*/
SELECT subjectName, credit, preSubject FROM subject
    WHERE completionClassification = 'majorRequired'
```
   
#### Example 2 of conditional query   
// 조건질의문 예시 2   
   
// 남학생 중 2000년 이전에 태어난 학생의 학생번호, 학생이름, 전화번호, 나이를 출력하시오   
- Please print out the student number, student name, phone number, and age of the student born before 2000 among male students   
   
```sql
/*
SELECT 학생번호, 학생이름, 전화번호, 나이 FROM 학생
    WHERE 성별 = '남' AND 생년월일 < '2000-01-01'
*/
SELECT studentNumber, studentName, phoneNumber, age FROM student
    WHERE Gender = 'Male' AND dateOfBirth < '2000-01-01'
```
   
#### Sorting of data   
// 데이터 정렬   
   
// ORDER BY 절을 사용   
// 검색 결과를 특정 컬럼에 대해 오름차순 또는 내림차순으로 정렬   
// - 오름차순 : ASC   
// - 내림차순 : DESC   
- Using the ORDER BY clause   
- Sort search results in ascending or descending order for a particular column   
  - Ascending order : ASC   
  - Descending order : DESC   
   
#### Syntax format of sorting of data   
// 데이터 정렬 구문 형식   
   
```sql
/*
SELECT 문 형식
    ORDER BY 컬럼1 [ASC|DESC],
             ...,
             컬럼2 [ASC|DESC]
*/
SELECT statement format
    ORDER BY column1 [ASC|DESC],
             ...,
             column2 [ASC|DESC]
```
   
#### Example of data sort   
// 데이터 정렬 예시   
   
// 학생의 계좌정보를 '잔액' 기준으로 각각 오름차순, 내림차순으로 정렬하시오   
- Sort the student's account information in ascending and descending order, respectively, based on 'balance'   
   
```sql
/*
SELECT * FROM 계좌
    ORDER BY 잔액 ASC
*/
SELECT * FROM account
    ORDER BY balance ASC
```
   
```sql
/*
SELECT * FROM 계좌
    ORDER BY 잔액 DESC
*/
SELECT * FROM account
    ORDER BY balance DESC
```
   
#### Special operator   
// 특수 연산자   
   
// 범위 포함 여부, 부분 이치 여부, 포함 여부 등 관계형 데이터베이스에서만 사용되도록 고안된 연산자   
- Operators designed to be used only in relational databases, such as whether to include a range, partial reason, and whether it is included or not   
   
|Type|Use Example|Meaning|
|:---:|:---|:---|
|BETWEEN|// 컬럼명 BETWEEN V1 AND V2<br />- columnName BETWEEN V1 AND V2|// 컬럼값이 V1 ~ V2 사이에 존재하는지 검사<br />- Examine if the column value exists between V1 and V2|
|LIKE|// 컬럼명 LIKE 'V1%'<br />- columnName LIKE 'V1%'|// V1으로 시작하는 문자열 검사<br />- String check beginning with V1|
|LIKE|// 컬럼명 LIKE '%V1'<br />- columnName LIKE '%V1'|// V1으로 끝나는 문자열 검사<br />- Check string ending in V1|
|LIKE|// 컬럼명 LIKE '%V1%'<br />- columnName LIKE '%V1%'|// V1이 문자열 내부에 존재하는지 검사<br />- Check if V1 exists inside the string|
|LIKE|// 컬럼명 LIKE 'V1_'<br />- columnName LIKE 'V1_'|// V1 뒤에 한 문자만 일치하는지 검사<br />- Check to see if only one letter matches after V1|
|IN|// 컬럼명 IN (V1, V2, ..., Vn)<br />- columnName IN (V1, V2, ..., Vn)|// 컬럼값이 V1, V2, ..., Vn 중 하나와 일치하는지 검사<br />- Check that the column value matches one of V1, V2, ..., Vn|
   
#### Example 1 of special operator   
// 특수 연산자 예시 1   
   
// 잔액이 20만원 이상 40만원 이하인 계좌의 계좌번호, 잔액, 학생번호를 출력하시오   
- Please print out the account number, balance, and student number of the account with a balance of 200,000 won or more and 400,000 won or less   
   
```sql
/*
SELECT 계좌번호, 잔액, 학생번호 FROM 계좌
    WHERE 잔액 >= 200000 ADN 잔액 <= 400000
*/
SELECT accountNumber, balance, studentNumber FROM account
    WHERE balance >= 200000 ADN balance <= 400000
```
   
```sql
/*
SELECT 계좌번호, 잔액, 학생번호 FROM 계좌
    WHERE 잔액 BETWEEN 200000 ADN 400000
*/
SELECT accountNumber, balance, studentNumber FROM account
    WHERE balance BETWEEN 200000 ADN 400000
```
   
#### Example 2 of special operator   
// 특수 연산자 예시 2   
   
// 소속학과가 '컴퓨터과학과', '행정학과', '법학과'인 교수의 교수이름, 직위, 소속학과를 출력하시오   
- Print out the professor's name, position, and affiliated department whose departments are Computer Science, Public Administration, and Law   
   
```sql
/*
SELECT 교수이름, 직위, 소속학과 FROM 교수
    WHERE 소속학과 = '컴퓨터과학과' OR
          소속학과 = '행정학과' OR
          소속학과 = '법학과'
*/
SELECT professorName, position, affiliatedDepartment FROM professor
    WHERE affiliatedDepartment = 'Department of Computer Science' OR
          affiliatedDepartment = 'Department of Public Administration' OR
          affiliatedDepartment = 'Department of Low'
```
   
```sql
/*
SELECT 교수이름, 직위, 소속학과 FROM 교수
    WHERE 소속학과 IN('컴퓨터과학과', '행정학과', '법학과')
*/
SELECT professorName, position, affiliatedDepartment FROM professor
    WHERE affiliatedDepartment IN('Department of Computer Science', 'Department of Public Administration', 'Department of Low')
```
   
#### Example 3 of special operator   
// 특수 연산자 예시 3   
   
// 과목코드가 'COM'으로 시작하는 과목의 과목코드, 과목명, 이수구분을 출력하시오   
- Please print out the subject code, subject name, and completion classification of the subject whose subject code starts with 'COM'   
   
```sql
/*
SELECT 과목코드, 과목명, 이수구분 FROM 과목
    WHERE 과목코드 LIKE 'COM%'
*/
SELECT subjectCode, subjectName, completionClassification FROM subject
    WHERE subjectCode LIKE 'COM%'
```
   
#### Concept of function   
// 함수의 개념   
   
// 특정 목적을 수행하도록 사전에 정의된 연산 및 기능을 수행한 후 결과값을 반환하는 명령어 집합   
- A set of commands that perform predefined operations and functions to serve a specific purpose and then return the result   
   
// 상용 DBMS는 검색 결과가 사용자에게 여러 형태로 사용되도록 여러 데이터 타입에 대한 다양한 함수를 제공 (MySQL 기준)   
// - 문자함수   
// - 숫자함수   
// - 날짜 및 시간함수   
- Commercial DBMS provides users with a variety of functions for multiple data types so that search results are used in multiple forms (based on MySQL)   
  - Character function   
  - Numerical function   
  - Date and time function   
   
#### Numerical function   
// 숫자함수   
   
// 삼각함수, 상수, 올림과 버림, 난수 등 숫자 데이터 타입에 적용할 수 있는 계산을 위한 함수   
- Functions for calculations applicable to numeric data types such as trigonometric functions, constants, ollim and discard, and random numbers   
   
|Type|Use Example|Meaning|
|:---|:---|:---|
|ABS()|ABS(X)|// X의 절대값을 반환<br />- Returns the absolute value of X|
|SIN(), COS(), etc.|SIN(X), etc.|// X의 삼각함수 값을 반환<br />- Returns the trigonometric value of X|
|CEILING(), FLOOR()|CEILING(X), FLOOR(X)|// X의 보다 크지 (작지) 않은 최소 (최대) 의 정수<br />- An integer of a minimum (maximum) that is not greater (not smaller) than X|
|LN()|LN(X)|// 자연 로그 InX의 값을 반환<br />- Returns the value of the natural log InX|
|PI()|PI()|// 원주율( ∏ ) 값을 반환<br />- Returns the circumference ( ∏ ) value|
|POWER()|POWER(X, Y)|// 거듭제곱 X<sup>Y</sup>의 값을 반환<br />- Return the value of power X<sup>Y</sup>|
|RAND()|RAND()|// 0과 1사이의 임의의 값을 반환<br />- Returns any value between 0 and 1|
|ROUNT()|ROUNT(X,[, Y])|// X의 Y번째 소수점 위치의 수를 반올림한 값을 반환<br />- Returns the value of X rounded to the Y-th decimal place|
|SQRT()|SQRT(X)|// X의 제곱근의 값을 반환<br />- Returns the value of the square root of X|
|TRUNCATE()|TRUNCATE(X, Y)|// X의 Y번째 소수점 이하를 버림한 값을 반환<br />- Returns the value of X minus the value below the Y-th decimal point|
   
#### Character function   
// 문자함수   
   
// 문자열 조작 및 문자 형식 변환 등의 문자와 관련된 다양한 연산을 지원하는 함수   
- Functions that support various operations related to characters, such as string manipulation and character format conversion   
   
|Type|Use Example|Meaning|
|:---|:---|:---|
|CHAR_LENGTH()|CHAR_LENGTH(X)|// X의 글자수를 반환 (한글도 1글자로 계산)<br />- Returns the number of characters in X (In Korean, one letter is counted)|
|CONCAT()|CONCAT(X, Y)|// X와 Y 문자열을 결합<br />- Combine X and Y strings|
|LOWER()|LOWER(X)|// X의 문자를 모두 소문자로 변환<br />- Convert all characters of X to lowercase|
|UPPER()|UPPER(X)|// X의 문자를 모두 대문자로 변환<br />- Convert all characters of X to uppercase|
|SUBSTRING()|SUBSTRING(X, A, B)|// X의 A번째 문자부터 B개의 문자열을 반환<br />- Returns as many strings as B from the A-th character of X|
|TRIM() / LTRIM() / RTRIM()|TRIM(X) / LTRIM(X) / RTRIM(X)|// 양쪽 / 왼쪽 / 오른쪽 공백 문자를 제거하고 반환<br />- Remove both / left / right blank characters and return|
   
#### Date function   
// 날짜함수   
   
// 날짜 및 시간 데이터 타입에 적용되어 산술 연산 및 시간 형 변환 등의 조작을 위한 함수   
- Function applied to date and time data types for operations such as arithmetic operations and time type conversion   
   
|Type|Use Example|Meaning|
|:---|:---|:---|
|ADDDATE()|ADDDATE(X, INTERVAL Y Unit)|// X에 Y 단위의 시간을 더한 날짜를 반환<br />- Returns the date X plus the time in Y units|
|ADDTIME()|ADDTIME(X, Y)|// X와 Y 시각을 더한 날짜를 반환<br />- Returns the date of the addition of the X and Y hours|
|CURDATE(), CURRENT_DATE()|CURDATE(), CURRENT_DATE()|// 현재 날짜를 반환<br />- Returns the current date|
|CURTIME(), CURRENT_TIME()|CURTIME(), CURRENT_TIME()|// 현재 시간을 반환<br />- Returns the current time|
|DATE()|DATE(X)|// X에서 날짜 (년, 월, 일) 을 반환<br />- Returns the date (year, month, day) of X|
|YEAR()|YEAR(X)|// X에서 년 값을 반환<br />- Returns the value of X year|
   
#### Example of function   
// 함수 예시   
   
// 학생의 학생번호, 학생이름, 성별을 출력하시오. 단, 학생번호는 앞 6자리만 출력하고 성별 뒤에는 '성'을 붙이시오   
- Please print out the student's student number, student name, and gender. However, please print only the first 6 digits of student number and put the last name after the gender   
   
```sql
/*
SELECT SUBSTRING(학생번호, 1, 6)
       , 학생이름
       , CONCAT(성별, '성')
    FROM 학생
*/
SELECT SUBSTRING(studentNumber, 1, 6)
       , studentName
       , CONCAT(Gender, 'Gender')
    FROM student
```
   
#### Aggregate Function   
// 집계 함수   
   
// 특정 컬럼에 집계 함수를 통해 다양한 통계 연산을 수행할 수 있는 기능   
// SELECT 절 또는 HAVING 절에서 사용   
- Ability to perform various statistical operations through aggregate functions on specific columns   
- Use in SELECT clause or HAVING clause   
   
// 집계 함수의 종류   
// - COUNT : 컬럼에 있는 값들의 개수   
// - SUM : 컬럼에 있는 값들의 합   
// - AVG : 컬럼에 있는 값들의 평균   
// - MAX : 컬럼에서 가장 큰 값   
// - MIN : 컬럼에서 가장 작은 값   
- Types of aggregate functions   
  - COUNT : Number of values in a column   
  - SUM : Sum of values in a column   
  - AVG : Average of the values in a column   
  - MAX : Largest value in a column   
  - MIN : Smallest value in a column   
   
#### Example 1 of aggregate function   
// 집계 함수 예시 1   
   
// 단과대학의 개수를 출력하시오   
- Please print out the number of colleges   
   
```sql
/*
SELECT COUNT(단과대학)
    FROM 학과
*/
SELECT COUNT(college)
    FROM department
```
   
// 중복값은 한번만 출력   
- Output duplicate values only once   
   
```sql
/*
SELECT COUNT(DISTINCT 단과대학)
    FROM 학과
*/
SELECT COUNT(DISTINCT college)
    FROM department
```
   
// 별칭 사용   
- Using Alias   
   
```sql
/*
SELECT COUNT(DISTINCT 단과대학) AS 단과대학수
    FROM 학과
*/
SELECT COUNT(DISTINCT college) AS numberOfColleges
    FROM department
```
   
#### Group query   
// 그룹 질의   
   
// 특정 기준으로 레코드를 그룹화하고 각 레코드 그룹에 대해 집계 함수를 적용하는 질의   
- Query that group records by specific criteria and apply aggregate functions for each group of records   
   
#### Syntax format of group query   
// 그룹 질의 구문 형식   
   
```sql
/*
SELECT 질의
    GROUP BY 컬럼
*/
SELECT query
    GROUP BY column
```
   
// 주의사항 : SELECT 절에 그룹의 기준과 집계 함수 이외의 컬럼은 포함될 수 없음   
- Caution : SELECT clause cannot contain columns other than group criteria and aggregate functions   
   
#### Example 1 of group query   
// 그룹 질의 예시 1   
   
// 소속학과별 교수의 수를 출력하시오   
- Print out the number of professors by affiliated department   
   
```sql
/*
SELECT 소속학과, COUNT(*) AS 교수수
    FROM 교수
    GROUP BY 소속학과
*/
SELECT affiliatedDepartment, COUNT(*) AS numberOfProfessors
    FROM professor
    GROUP BY affiliatedDepartment
```
   
#### HAVING clause   
// HAVING 절   
   
// 그룹 질의의 결과 레코드에 대해 출력 조건을 기술하기 위한 절   
- Clause to describe output conditions for the result record of a group query   
   
#### Syntax format of HAVING clause   
// HAVING 절 구문 형식   
   
```sql
/*
SELECT 질의
    GROUP BY 컬럼
        HAVING 조건
*/
SELECT query
    GROUP BY column
        HAVING condition
```
   
#### Conditions description clause   
// 조건 기술 절   
   
// WHERE   
// - 레코드에 대한 조건을 기술   
// HAVING   
// - 집계 결과 (GROUP BY 한 결과) 레코드에 대한 조건을 기술   
- WHERE   
  - Description of conditions for records   
- HAVING   
  - Describes conditions for aggregated results (as a result of GROUP BY) records   
   
#### Example 2 of group query   
// 그룹 질의 예시 2   
   
// 2개 이상의 전공을 신청한 학생의 학생번호와 신청 전공수를 출력하시오   
- Please print out the student number of the student who applied for more than two majors and the number of majors that the student applied for   
   
```sql
/*
SELECT 학생번호, COUNT(*) AS 신청_전공수
    FROM 전공
    GROUP BY 학생번호
        HAVING 신청_전공수 >= 2
*/
SELECT studentNumber, COUNT(*) AS NumberOfMajorSubjectsApplied
    FROM major
    GROUP BY studentNumber
        HAVING NumberOfMajorSubjectsApplied >= 2
```
   
#### Nesting query   
// 중첩 질의   
   
// SELECT 문 내부에서 독립적으로 실행 가능한 또 다른 SELECT 문이 내포되어 있는 질의   
// 일반적으로 내부 질의의 처리결과를 외부 질의에서 재사용   
- A query that contains another SELECT statement that is independently executable inside the SELECT statement   
- Typically, the processing results of an inner query are reused in an outer query   
   
// 중첩 질의의 종류   
// - FROM 절에서의 중첩 질의 활용   
// -- FROM 절에서의 결과 집합을 SELECT 에서 재검색   
// - WHERE 절에서의 중첩 질의 활용   
// -- WHERE 절에서의 결과 집합을 활용하여 외부 질의에서 레코드의 출력 여부를 결정   
// -- IN, NOT IN, EXISTS, NOT EXSISTS 사용   
- Type of nesting query   
  - Leveraging nesting query in FROM clause   
    - Researching the result set in FROM clause in SELECT statement   
  - Leveraging nesting query in WHERE clause   
    - Use the set of results in WHERE clause to determine whether records are output from an outer query   
    - Using IN, NOT IN, EXISTS, NOT EXSISTS   
   
#### Syntax format of nesting query   
// 중첩 질의 구문 형식   
   
```sql
/*
SELECT 컬럼1, 컬럼2, ..., 컬럼N
    FROM (SELECT 컬럼1, 컬럼2, ..., 컬럼M
              FROM 테이블
              WHERE 조건)
    WHERE 조건
*/
SELECT column1, column2, ..., columnN
    FROM (SELECT column1, column2, ..., columnM
              FROM table
              WHERE condition)
    WHERE condition
```
   
```sql
/*
SELECT 컬럼1, 컬럼2, ..., 컬럼N
    FROM 테이블1
    WHERE 컬럼I 연산자 (SELECT 컬럼J
                          FROM 테이블2
                          WHERE 조건)
*/
SELECT column1, column2, ..., columnN
    FROM table1
    WHERE columnI operator (SELECT columnJ
                              FROM table2
                              WHERE condition)
```
   
#### Example 1 of nesting query   
// 중첩 질의 예시 1   
   
// 학과별 교수의 평균연봉이 70,000,000 미만인 학과 중 가장 높은 평균연봉을 출력하시오   
- Output the highest average annual salary among the departments in which the average annual salary of professors in each department is less than 70,000,000   
   
```sql
/*
SELECT MAX(d.평균연봉) AS 평균연봉
    FROM (SELECT 소속학과, AVG(연봉) AS 평균연봉
              FROM 교수
              GROUP BY 소속학과) AS d
    WHERE d.평균연봉 < 7000000
*/
SELECT MAX(d.averageAnnualSalary) AS averageAnnualSalary
    FROM (SELECT affiliatedDepartment, AVG(annualSalary) AS averageAnnualSalary
              FROM professor
              GROUP BY affiliatedDepartment) AS d
    WHERE d.averageAnnualSalary < 7000000
```
   
#### Example 2 of nesting query   
// 중첩 질의 예시 2   
   
// '생활과학과' 소속 학생 중 수강신청을 하지 않은 학생의 학생번호를 출력하시오   
- Please print out the student number of the students in the 'Life Science Department' who did not register for the course   
   
```sql
/*
SELECT A.학생번호
    FROM 전공 AS A
    WHERE A.학과이름 = '생활과학과' AND NOT EXISTS(SELECT B.학생번호
              FROM 수강 B
              WHERE A.학생번호 = B.학생번호)
*/
SELECT A.studentNumber
    FROM major AS A
    WHERE A.departmentName = 'Life Science Department' AND NOT EXISTS(SELECT B.studentNumber
              FROM registrationForCourses B
              WHERE A.studentNumber = B.studentNumber)
```
   
// 전공 A의 학생번호를 기준으로 수강 B에 존재하지 않는 학생번호인 경우 출력하는 것임   
- Based on the student number of major A, if the student number does not exist in registrationForCourses B, it is printed out   
   
#### Join query   
// 조인 질의   
   
// 테이블 간의 관련성을 이용하여 두 개 이상의 테이블에서 데이터를 검색하는 질의 기법   
// ER 모델링 및 정규화 기법으로 여러 테이블로 분리된 정보를 통합하여 검색 시 유용함   
- Query techniques to search data from two or more tables using relevance between tables   
- ER modeling and regularization techniques are useful for searching by integrating information separated into multiple tables   
   
// 조인 질의의 종류   
// - 내부 조인   
// - 외부 조인   
- Type of join query   
  - INNER JOIN   
  - OUTER JOIN   
   
#### INNER JOIN   
// 내부 조인   
   
// 두 개 이상의 테이블에서 조인조건을 만족하는 레코드만 결합하여 출력 결과에 포함시키는 연산   
// 조인조건은 WHERE 절이 아닌 ON 절에 작성   
- Operations that combine only records that satisfy join conditions in two or more tables and include them in the output results   
- Join conditions are prepared in ON clause, not WHERE clause   
   
// ANSI SQL ISO 표준과 사실상의 표준인 오라클 (Oracle) 사 가 제안한 조인 형식이 사용됨   
- The join format proposed by the ANSI SQL ISO standard and the de facto standard Oracle is used   
   
#### Syntax format of INNER JOIN   
// 내부 조인 구문 형식   
   
```sql
/*
SELECT 컬럼1, 컬럼2, ..., 컬럼M,
    FROM 테이블1 INNER JOIN 테이블2
    ON 조인조건1
    [WHERE 조건]
*/
SELECT column1, column2, ..., columnM,
    FROM table1 INNER JOIN table2
    ON joinCondition1
    [WHERE condition]
```
   
#### Example of INNER JOIN   
// 내부 조인 예시   
   
// 나이가 30세 이상인 학생의 학생이름과 나이, 그리고 그 학생이 소유한 계좌의 계좌번호, 잔액을 출력하시오   
- Please print out the student name and age of the student who is over 30 years old, and the account number and balance of the student's account   
   
// ANSI SQL ISO 표준   
- ANSI SQL ISO Standard   
   
```sql
/*
SELECT 학생.학생이름, 학생.나이, 계좌.계좌번호, 계좌.잔액
    FROM 학생 INNER JOIN 계좌
    ON 학생.학생번호 = 계좌.학생번호
    WHERE 학생.나이 >= 30
*/
SELECT student.studentName, student.age, account.accountNumber, account.balance
    FROM student INNER JOIN account
    ON student.studentNumber = account.studentNumber
    WHERE student.age >= 30
```
   
// 오라클 (Oracle) 사   
- Oracle   
   
```sql
/*
SELECT 학생.학생이름, 학생.나이, 계좌.계좌번호, 계좌.잔액
    FROM 학생, 계좌
    WHERE 학생.학생번호 = 계좌.학생번호 AND 학생.나이 >= 30
*/
SELECT student.studentName, student.age, account.accountNumber, account.balance
    FROM student, account
    WHERE student.studentNumber = account.studentNumber AND student.age >= 30
```
   
#### NATURAL JOIN   
// 자연 조인   
   
// 두 개 이상의 테이블을 하나의 테이블로 결합하는 내부 조인과 매우 유사한 기능   
// 두 테이블에 동일한 이름의 컬럼에 대해 값이 같은 레코드를 결합하는 내부 조인   
- It is a function very similar to the inner join that combines two or more tables into one table   
- An inner join that combines two tables with records of the same value for columns of the same name   
   
#### Syntax format of NATURAL JOIN   
// 자연 조인 구문 형식   
   
```sql
/*
SELECT 컬럼1, 컬럼2, ..., 컬럼M,
    FROM 테이블1 NATURAL JOIN 테이블2
    [WHERE 조건]
*/
SELECT column1, column2, ..., columnM,
    FROM table1 NATURAL JOIN table2
    [WHERE condition]
```
   
#### OUTER JOIN   
// 외부 조인   
   
// 내부 조인 (inner join) 은 조인조건에 일치하는 레코드만 결합하여 결과를 생성   
// - 조인 결과에 정보의 손실이 발생   
- An inner join combines only the records that match the join condition to produce a result   
  - Loss of information in join result   
   
// 외부 조인은 조인조건에 맞지 않는 레코드도 질의의 결과에 포함시키는 질의   
- An outer join is a query that includes records that do not meet the join condition in the query's results   
   
// 외부 조인의 종류   
// - 왼쪽 외부 조인 (left outer join)   
// - 오른쪽 외부 조인 (right outer join)   
// - 완전 외부 조인 (full outer join)   
- Type of outer join   
  - left outer join   
  - right outer join   
  - full outer join   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/databaseSystemsJoinConcept1.png)
   
#### Syntax format of OUTER JOIN   
// 외부 조인 구문 형식   
   
```sql
/*
SELECT 별칭1.컬럼1, 별칭1.컬럼2, ..., 별칭1.컬럼M,
       별칭2.컬럼1, 별칭2.컬럼2, ..., 별칭2.컬럼N,
    FROM 테이블1 AS 별칭1
         LEFT|RIGHT [OUTER] JOIN
         테이블2 AS 별칭2
    ON 별칭1.컬럼I = 별칭2.컬럼J
    [WHERE 절]
*/
SELECT alias1.column1, alias1.column2, ..., alias1.columnM,
       alias2.column1, alias2.column2, ..., alias2.columnN,
    FROM table1 AS alias1
         LEFT|RIGHT [OUTER] JOIN
         table2 AS alias2
    ON alias1.columnI = alias2.columnJ
    [WHERE clause]
```
   
#### Example of OUTER JOIN   
// 외부 조인 예시   
   
// 학생의 학생번호, 학생이름과 그 학생이 수강신청한 과목의 과목코드, 신청시각을 출력하시오. 단, 수강신청을 하지 않은 학생도 결과에 포함시키고 과목코드를 기준으로 오름차순 정렬한다   
- Please print out the student's student number, student name, subject code of the subject the student registered for, and application time. However, students who have not registered for the course are also included in the results, and are sorted in ascending order based on the subject code   
   
```sql
/*
SELECT A.학생번호, A.학생이름, B.과목코드, B.신청시각
    FROM 학생 AS A LEFT OUTER JOIN 수강 AS B
    ON A.학생번호 = B.학생번호
    ORDER BY B.과목코드 ASC
*/
SELECT A.studentNumber, A.studentName, B.subjectCode, B.applicationTime
    FROM student AS A LEFT OUTER JOIN registrationForCourses AS B
    ON A.studentNumber = B.studentNumber
    ORDER BY B.subjectCode ASC
```
   
#### Self-Join   
// 셀프 조인   
   
// 한 테이블이 자기 자신과 조인되는 형태   
// 동일한 이름의 테이블에 대한 조인이므로 반드시 테이블 이름에 대한 별칭을 의무적으로 사용해야 함   
- A format in which a table is joined with itself   
- Since it is a join for a table with the same name, it is mandatory to use an alias for the table name   
   
#### Syntax format of Self-Join   
// 셀프 조인 구문 형식   
   
```sql
/*
SELECT 별칭1.컬럼1, 별칭1.컬럼2, ..., 별칭1.컬럼M,
       별칭2.컬럼1, 별칭2.컬럼2, ..., 별칭2.컬럼N,
    FROM 테이블1 AS 별칭1
         INNER|OUTER JOIN 테이블2 AS 별칭2
    ON 조인조건
    [WHERE 절]
*/
SELECT alias1.column1, alias1.column2, ..., alias1.columnM,
       alias2.column1, alias2.column2, ..., alias2.columnN,
    FROM table1 AS alias1
         INNER|OUTER JOIN table2 AS alias2
    ON joinCondition
    [WHERE clause]
```
   
#### Example of Self-Join   
// 셀프 조인 예시   
   
// 과목의 과목코드, 과목명 그리고 그 과목의 선수과목의 과목코드, 과목명을 모두 출력하시오. 단, 선수과목이 없는 과목도 결과에 포함시킨다   
- Please print out the subject code, subject name, and print out the subject code and subject name of the preceding subject of the subject. However, the results include subjects that do not have a preceding course   
   
```sql
/*
SELECT B.과목명, B.과목코드
       A.과목명 AS 선수과목명, A.과목코드 AS 선수과목코드
    FROM 과목 AS A RIGHT OUTER JOIN 과목 AS B
    ON A.과목코드 = B.선수과목
*/
SELECT B.subjectName, B.subjectCode
       A.subjectName AS preSubjectName, A.subjectCode AS preSubjectCode
    FROM subject AS A RIGHT OUTER JOIN subject AS B
    ON A.subjectCode = B.preSubject
```
   
<br />
### Using View (Virtual Table)   
// 뷰의 사용   
   
#### Concept of view   
// 뷰의 개념   
   
// 데이터를 저장하고 있는 하나 이상의 테이블을 유도하여 생성하는 가상의 테이블 (virtual table)   
// - 데이터 독립성   
// -- 원본 테이블의 구조가 바뀌어도 뷰를 이용한 작업은 정의만 변경되어 응용 프로그램에 영향이 없음   
// - 데이터 보안   
// -- 사용자에게 원본 테이블의 일부 컬럼에 대한 접근을 허용하여 보안 효과를 향상   
// - 다양한 구조의 테이블 사용   
// -- 사용자의 요구사항에 맞는 테이블의 구조를 제공   
// - 작업의 단순화   
// -- 복잡한 질의문을 뷰로 단순화   
// - 데이터 무결성   
// -- WITH CHECK OPTION 을 이용하여 뷰 생성에 위배되는 수정작업을 거부   
- A virtual table that derives and generates one or more tables storing data   
  - Data Independence   
    - Changes in the structure of the source table do not affect the application because the operation using the view changes only the definition   
  - Data Security   
    - Increase security by allowing users access to some columns in the source table   
  - Using tables of various structures   
    - It provides the structure of the table to suit the needs of the user   
  - Simplifying tasks   
    - Simplifying complex query into views   
  - Data Integrity   
    - Use With CHECK OPTION to reject modifications that violate view creation   
   
#### Creating the view   
// 뷰의 생성   
   
// 생성되는 뷰의 구조는 SELECT 문의 결과로 결정   
- The structure of the created view is determined by the result of the SELECT statement   
   
#### Syntax format of view   
// 뷰 구문 형식   
   
```sql
/*
CREATE VIEW 뷰이름 AS
    (SELECT 컬럼1, 컬럼2, ..., 컬럼N
        FROM 테이블
        [WHERE 조건])
[WITH CHECK OPTION]
*/
CREATE VIEW viewName AS
    (SELECT column1, column2, ..., columnN
        FROM table
        [WHERE condition])
[WITH CHECK OPTION]
```
   
#### Modify view   
// 뷰의 수정   
   
// 뷰의 수정은 생성과 동일하게 새로운 SELECT 문의 결과로 변경   
- The modification of the view is changed to the result of a new SELECT statement, the same as the creation   
   
```sql
/*
ALTER VIEW 뷰이름(컬럼1, 컬럼2, ..., 컬럼N) AS
    (SELECT 컬럼1, 컬럼2, ..., 컬럼N
        FROM 테이블
        [WHERE 조건])
*/
ALTER VIEW viewName(column1, column2, ..., columnN) AS
    (SELECT column1, column2, ..., columnN
        FROM table
        [WHERE condition])
```
   
#### Delete view   
// 뷰의 삭제   
   
```sql
/*
DROP VIEW 뷰이름
*/
DROP VIEW viewName
```
   
#### Example of create view   
// 뷰 생성 예시   
   
// '컴퓨터과학과' 소속의 학생정보와 학과이름 및 이수학점을 출력하는 '컴퓨터과학과_학생' 뷰를 생성하시오   
- Create a Computer Science_Student view that outputs student information, department name, and completion credits belonging to the 'Department of Computer Science'   
   
```sql
/*
CREATE VIEW 컴퓨터과학과_학생 AS
(SELECT 학생.*, 전공.학과이름, 전공.이수학점
     FROM 학생 NATURAL JOIN 전공
     WHERE 전공.학과이름 = "컴퓨터과학과"
)
*/
CREATE VIEW departmentOfComputerScience_student AS
(SELECT student.*, major.departmentName, major.completionCredit
     FROM student NATURAL JOIN major
     WHERE major.departmentName = "Department of Computer Science"
)
```
   
#### Search and modify with a view   
// 뷰를 이용한 검색 및 수정   
   
// 뷰는 가상의 테이블이므로 데이터 조작은 테이블 조작과 동일하게 수행   
- Because a view is a virtual table, data manipulation is performed in the same way as table manipulation   
   
#### Syntax format of view search   
// 뷰 검색 구문 형식   
   
```sql
/*
SELECT 컬럼1, ..., 컬럼2
    FROM 뷰이름
    WHERE 조건
*/
SELECT column1, ..., column2
    FROM viewName
    WHERE condition
```
   
#### Formatting View Search Execution   
// 뷰 검색 실행 형식   
   
```sql
/*
SELECT 컬럼1, ..., 컬럼2
    FROM 뷰이름
    WHERE 조건 AND 뷰정의조건
*/
SELECT column1, ..., column2
    FROM viewName
    WHERE condition AND viewDefinitionConditions
```
   
<br />
### Insert data using view   
// 뷰를 이용한 데이터 삽입   
   
// 뷰에 대한 INSERT 문은 원본 테이블에서 실행   
// - PRIMARY KEY, NOT NULL 등의 제약사항이 위배되는 경우 삽입이 불가능   
// - 원본 테이블에 존재하는 컬럼이지만 뷰에는 없는 컬럼에 삽입하는 경우 실행 불가능   
// - 조인 질의 또는 그룹 질의가 적용된 뷰는 데이터 삽입 및 수정이 불가능   
// - WITH CHECK OPTION 이 적용된 뷰는 위배되는 사항이 없더라도 뷰에 맞지 않는 조건일 경우 실행 불가능   
- The INSERT statement for the view is executed in the original table   
  - Unable to insert if restrictions such as PRIMARY KEY and NOT NULL are violated   
  - Infeasible when inserted into a column that is present in the source table but not in the view   
  - Views with join queries or group queries cannot be inserted or modified   
  - A view with WITH CHECK OPTION cannot be executed under conditions that do not fit the view, even if there is no violation   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
