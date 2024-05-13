---
layout: post
title:  "Database Systems: SQL"
date:   2024-05-12 09:00:00 +0900
categories: [Database Systems]
---

### 
// SQL (Structured Query Language) 의 개요

// 관계대수에 기초하여 RDBMS의 데이터 관리를 위해 설계된 언어
// 1986년 ANSI, 1987년 ISO에서 표준으로 제정
// - SQL-86, SQL-89, SQL-92, SQL:1999, SQL:2003, SQL:2008
// - 상용 DBMS의 특성에 맞게 국제표준을 확장한 독자적 버전이 존재
// 특징
// - 비절차적 (선언형) 언어, 필요한 데이터만 기술
// - 인간의 언어와 매우 유사하고 간단, 명료함
- 
- 
  - 
  - 
  - 
  - 

<br />
### 
// SQL의 구성

// 데이터 정의 언어 
// - 데이터베이스 내의 객체를 생성 및 삭제하고 그 구조를 조작하는 명령어의 집합
// - 데이터가 준수해야 하는 제약조건을 기술
// - CREATE, ALTER, DROP 문 등
- DDL (Data Definition Language)
  - 
  - 
  - 

// 데이터 조작 언어
// - DDL에 의해 정의된 테이블에 데이터를 조작하는 명령어의 집합
// - 데이터에 대한 CRUD (생성, 검색, 삭제, 수정) 명령을 포함
// - INSERT, UPDATE, DELETE, SELECT 문 등
- DML (Data Manipulation Language)
  - 
  - 
  - 

// 데이터 제어 언어
// - 데이터베이스에 접근하고 객체들을 사용하도록 권한을 주고 회수하는 명령어의 집합
// - GRANT, REVOKE 문 등
- DCL (Data Control Language)
  - 
  - 

<br />
### DDL (Data Definition Language)
// 데이터 정의 언어

#### 
// 데이터 정의 언어의 개념 

// 데이터베이스 객체를 생성, 삭제 또는 구조를 수정하는 명령어의 집합
- 

// 데이터베이스 객체의 종류
// - 데이터 저장 : 테이블, 인덱스, 뷰
// - 데이터 조작 : 트리거, 프로시저, 함수 등
- 
  - 
  - 

// 데이터 정의 명령어의 종류
// - CREATE : 객체 생성
// - ALTER : 객체 수정
// - DROP : 객체 삭제
- 
  - 
  - 
  - 

#### 
// 스키마 정의

// 스키마 = 데이터베이스
// 한 조직의 데이터베이스 시스템의 운영에 필요한 테이블, 인덱스, 뷰 등의 데이터베이스 객체의 집합
- 
- 

// 스키마 관리 방법
// - Forward Engineer
// - SQL 에디터
// - 내비게이터 패널
- 
  - 
  - 
  - 

// 스키마 관리 구문 형식
// - 스키마 생성 : `CREATE SCHEMA 스키마 이름`
// - 스키마 삭제 : `DROP SCHEMA 스키마 이름`
- 
  - 
  - 

#### 
// 테이블 정의

// 새로운 2차원 형태의 테이블을 생성
- 

// 구문 형식
- 

```sql
CREATE TABLE 테이블이름(
    <컬럼1><데이터타입1>[제약조건1][,
    <컬럼2><데이터타입2>[제약조건2]]
    ... [,
    <컬럼n><데이터타입n>[제약조건n]]
    [PRIMARY KEY 컬럼명]
    [UNIQUE 컬럼명]
    [FOREIGN KEY 컬럼 REFERENCES 테이블이름(컬럼)]
)
```

#### 
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
CREATE TABLE 교수(
    교수번호 CHAR(13) NOT NULL,
    교수이름 CHAR(30) NOT NULL,
    직위 CHAR(10) NOT NULL,
    소속학과 CHAR(50) NOT NULL,
    연봉 INT NOT NULL)
```

#### 
// 데이터 타입의 개념

// 컬럼이 가질 수 있는 값의 범위, 즉 도메인을 결정
// 프로그래밍 언어에서의 변수를 생성하는 데이터 타입의 사용목적과 방법이 매우 유사
// 기본 데이터 타입
// - 문자 : CHAR(n), VARCHAR(n), TEXT
// - 숫자 : INT, FLOAT, DOUBLE, DECIMAL(m, n)
// - 날짜/시간 : DATE, TIME, DATETIME, TIMESTAMP
- 
- 
- 
  - 
  - 
  - 

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
- 
  - 
    - 
    - 
    - 
  - 
    - 
    - 
    - 
  - 
    - 
    - 
    - 
  - 
    - 
    - 

// 실수 데이터 타입
// - 고정 소수형
// -- DECIMAL(M, N) : 전체 M 자리, 소수점 이하 N 자리의 숫자
// --- 예시 : DECIMAL(5, 2) 는 -999.99 ~ 999.99
// -- NUMERIC - DECIMAL과 동일
// - 부동 소수형
// -- FLOAT : 4바이트 크기 부동 소수
// -- FLOAT(P) : 소수점 이하 P개 자리의 부동 소수
// -- DOUBLE - 8바이트 크기 부동 소수형
- 
  - 
    - 
      - 
    - 
  - 
    - 
    - 
    - 

// 날짜 데이터 타입
// - DATE : `YYYY-MM-DD` 형식의 시간
// - YEAR : `YYYY` 형식의 연도
- 
  - 
  - 

// 시간 데이터 타입
// - TIME : `HH:MI:SS` 형식의 시간
- 
  - 

// 날짜 및 시간 데이터 타입
// - DATETIME : `YYYY-MM-DD HH:MI:SS` 형식의 날짜 및 시간
// - TIMESTAMP : DATETIME과 동일
- 
  - 
  - 

// 문자 데이터 타입
// - CHAR(N) : 최대 길이가 N인 고정길이 문자열
// - VARCHAR(N) : 최대 길이가 N인 가변길이 문자열
// - TEXT, CLOB : 길이가 최대 2 ~ 4 GB 인 가변길이 문자열
// - ENUM : 유한개의 문자열 집합 중 하나의 값을 선택
// -- 성별 : ENUM('남', '여')
// -- 혈액형 : ENUM('A', 'B', 'O', 'AB')
- 
  - 
  - 
  - 
  - 
    - 
    - 

// 문자열 저장 예시
// - `DATABASE` 문자열 저장 시
// -- CHAR(10) 으로 저장 시 `DATABASE널널` 
// -- VARCHAR(10) 으로 저장 시 `DATABASE` 
- 
  - 
    - 
    - 

#### 
// 테이블 수정

// 생성된 테이블에 컬럼을 추가, 수정 (이름, 데이터 타입, 제약조건) 또는 삭제하는 명령
// 컬럼 삭제 또는 컬럼의 데이터 타입 수정 시 데이터에 대한 소실이 발생하므로 많은 주의가 요구됨
// 테이블 수정 방법
// - SQL 구문
// - 내비게이터 패널
- 
- 
- 
  - 
  - 

#### 
// 테이블 수정 구문 형식

```sql
# 컬럼 추가
ALTER TABLE 테이블이름
    [ADD COLUMN 컬럼 데이터타입 [제약조건]]
# 컬럼 삭제
ALTER TABLE 테이블이름
    [DROP COLUMN 컬럼이름]
# 컬럼 이름 변경
ALTER TABLE 테이블이름
    [CHANGE COLUMN 수정전컬럼이름 수정후컬럼이름]
# 컬럼 데이터타입 변경
ALTER TABLE 테이블이름
    [MODIFY COLUMN 컬럼 데이터타입]
```

#### 
// 테이블 수정 질의 예시

// 교수 테이블에 데이터 타입이 INT인 나이 컬럼을 추가하시오
- 

```sql
ALTER TABLE 교수
    ADD COLUMN 나이 INT
```

#### 
// 테이블 삭제

// 존재하는 테이블을 스키마에서 삭제
// 삭제할 테이블의 모든 데이터가 소실되고, 복구가 불가능한 연산이므로 각별한 주의가 요구됨
- 
- 

// 테이블 삭제 방법
// - SQL 구문
// - 내비게이터 패널
- 
  - 
  - 

#### 
// 테이블 삭제 구문 형식

```sql
DROP TABLE 테이블이름
```

#### 
// 제약조건

// 테이블과 테이블에 존재하는 데이터를 보다 무결하게 관리하기 위한 목적으로 사용
// DBMS는 테이블 조작 시 테이블에 정의된 제약조건을 만족시키는지 지속적으로 검사함
// DBMS는 적용하려는 제약의 유형에 따라 다양한 제약 조건을 지원함
- 
- 
- 

// 제약 조건의 종류
// - PRIMARY KEY : 기본키 지정, UNIQUE 와 NOT NULL 특성
// - FOREIGN KEY : 외래키 지정, 참조 컬럼 정의
// - NOT NULL : NULL이 될 수 없는 컬럼에 지정
// - UNIQUE : 동일한 컬럼값을 가질 수 없음을 지정
// - AUTO_INCREMENT : 레코드가 추가될 때 자동적으로 속성값이 1부터 1씩 증가되어 입력
// - CHECK : 컬럼값이 특정 조건 준수 여부 지정
- 
  - 
  - 
  - 
  - 
  - 
  - 

#### 
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
CREATE TABLE 교수(
    교수번호 CHAR(13) NOT NULL,
    교수이름 CHAR(30) NOT NULL,
    직위 CHAR(10) NOT NULL,
    소속학과 CHAR(50) NOT NULL,
    연봉 INT NOT NULL
    PRIMARY KEY(교수번호),
    FOREIGN KEY(소속학과) REFERENCES 학과(학과이름)
)
```

<br />
### DML (Data Manipulation Language)
// 데이터 조작 언어

#### 
// 데이터 조작 언어의 개념 

// 정의된 테이블에 레코드에 삽입, 수정, 삭제 및 검색하는데 사용되는 명령어의 집합
- 

// 명령어의 종류
// - INSERT : 테이블 스키마에 적합한 레코드를 삽입
// - UPDATE : 테이블에서 조건을 만족하는 특정 레코드의 컬럼값을 수정
// - DELETE : 테이블에 조건을 만족하는 특정 레코드를 삭제
// - SELECT : 조건을 만족하는 레코드를 테이블에서 검색
- 
  - INSERT : 
  - UPDATE : 
  - DELETE : 
  - SELECT : 

#### INSERT
// 데이터 삽입

// 테이블에 새로운 레코드를 삽입하는 명령문
// - 테이블에 새로운 레코드를 삽입
// - 모든 속성 또는 부분 속성에 대한 속성값을 삽입

#### 
// 데이터 삽입 구문 형식

```sql
INSERT INTO 테이블이름
    VALUES(값1, 값2, ..., 값n)
```

```sql
INSERT INTO 테이블이름(컬럼1, 컬럼2, ..., 컬럼n)
    VALUES(값1, 값2, ..., 값n)
```

#### 
// 데이터 삽입 예시 1

// 학과이름 '영어영문학과', 단과대학 '인문과학대학', 주소 'http://abc.ac.kr', 전화번호 'O1O-OOOO-OOOO', 졸업학점 135 인 레코드를 학과 테이블에 삽입하시오
- 

```sql
INSERT INTO 학과
    VALUES('영어영문학과', '인문과학대학', 'http://abc.ac.kr', 'O1O-OOOO-OOOO', 135)
```

#### 
// 데이터 삽입 예시 2

// 단과대학 '자연과학대학', 학과이름 '농학과', 졸업학점 140, 전화번호 'O1O-OOOO-OOOO' 인 레코드를 학과 테이블에 삽입하시오
- 

```sql
INSERT INTO 학과(단과대학, 학과이름, 졸업학점, 전화번호)
    VALUES('자연과학대학', '농학과', 140, 'O1O-OOOO-OOOO')
```

#### UPDATE
// 데이터 수정

// 조건을 만족하는 레코드의 특정 컬럼값을 수정
- 

#### 
// 데이터 수정 구문 형식

```sql
UPDATE 테이블이름
    SET 컬럼1 = 값1[, 컬럼2 = 값2, ..., 컬럼n = 값n]
    [WHERE 조건]
```

```sql
UPDATE 테이블이름
    SET 컬럼1 = 수식1[, 컬럼2 = 수식2, ..., 컬럼n = 수식n]
    [WHERE 조건]
```

#### 
// 데이터 수정 예시 1

// 학과이름이 '농학과' 인 레코드의 주소 컬럼값을 'http://abc.ac.kr' 로 수정하시오
- 

```sql
UPDATE 학과
    SET 주소 = 'http://abc.ac.kr'
    WHERE 학과이름 = '농학과'
```

#### 
// 데이터 수정 예시 2

// 잔액이 500,000원 이상인 학생 계좌에 2% 이자를 지급하시오
- 

```sql
UPDATE 학과
    SET 잔액 = 잔액 * 1.02
    WHERE 잔액 >= 500000
```

#### DELETE
// 데이터 삭제

// 조건에 일치하는 레코드 집합을 테이블에서 삭제할 때 사용하는 명령어
- 

#### 
// 데이터 삭제 구문 형식

```sql
DELETE FROM 테이블이름
    [WHERE 조건]
```

#### 
// 데이터 삭제 예시 1

// 소속학과가 '행정학과'인 교수의 레코드를 삭제하시오
- 

```sql
DELETE FROM 교수
    WHERE 소속학과 = '행정학과'
```

#### 
// 데이터 삭제 예시 2

// 모든 강의 레코드를 삭제하시오
- 

```sql
DELETE FROM 과목
```

#### SAFE UPDATES
// SAFE UPDATES 모드

// WHERE절이 없는 UPDATE/DELETE 문은 테이블의 전체 레코드를 변경/삭제할 수 있음
// 의도하지 않은 데이터 변경/삭제 방지를 위해 MySQL은 SAFE UPDATES 모드를 지원
// 기본키가 아닌 컬럼을 대상으로 수정/삭제 조건을 명시할 경우 실행 여부를 결정
- 
- 
- 

#### 
// SAFE UPDATES 구문 형식

```sql
SET SQL_SAFT_UPDATES = 0 또는 1
```

<br />
### SELECT
// 데이터 검색

// 한 개 이상의 테이블에서 주어진 조건에 만족하는 레코드를 출력하는 명령문
// 관계 대수의 셀렉션, 프로젝션, 조인, 카티션 프로덕트 연산자의 기능을 모두 포함하고 있는 명령문
// 필수적 절인 SELECT 절과 부가적인 목적으로 사용할 수 있는 여러 절을 혼합하여 검색 기능을 구체화
- 
- 
- 

#### 
// SELECT 문 구문 형식

```sql
SELECT [DISTICT] 컬럼1, 컬럼2, ..., 컬럼n
    FROM 테이블1 [INNER JOIN | OUTER JOIN
         테이블2 INNER JOIN | OUTER JOIN
         ON 조인 조건1
         테이블3
         ..., INNER JOIN | OUTER JOIN
         테이블m]
    [ON 조인 조건식]
    [WHERE 조건식 [중첩질의]]
    [GROUP BY 컬럼1, 컬럼2, ..., 컬럼y]
        [HAVING 조건]]
    [ORDER BY 컬럼1[ASC|DESC], ..., 컬럼z[ASC|DESC]]
```

#### 
// SELECT 문의 각 절의 기능

// SELECT 절 : 결과에 포함되는 컬럼을 지정
// FROM 절 : 질의를 적용할 테이블을 지정
// ON/WHERE 절 : 조인 조건/검색할 레코드 조건을 지정
// GROUP BY 절 : 레코드를 그룹화하기 위한 그룹 조건을 지정
// HAVING 절 : GROUP BY 절이 적용된 결과에 대한 조건을 지정
// ORDER BY 절 : 검색 결과의 정렬 기준을 지정
- 
- 
- 
- 
- 
- 



#### 
// 단순질의문

// 
// 
// 
// 
// 
// 

#### 
// 조건질의문

// 
// 
// 
// 
// 
// 

#### 
// 특수연산자

// 
// 
// 
// 
// 
// 

#### 
// 함수

// 
// 
// 
// 
// 
// 

#### 
// 

// 
// 
// 
// 
// 
// 

#### 
// 

// 
// 
// 
// 
// 
// 

#### 
// 

// 
// 
// 
// 
// 
// 



<br />
### 
// 

// 
// 
// 
// 
// 
// 

#### 
// 

// 
// 
// 
// 
// 
// 

#### 
// 

// 
// 
// 
// 
// 
// 

#### 
// 

// 
// 
// 
// 
// 
// 

#### 
// 

// 
// 
// 
// 
// 
// 

   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
