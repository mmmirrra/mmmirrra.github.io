---
layout: post
title:  "MariaDB: sql"
date:   2024-01-03 09:00:00 +0900
categories: [MariaDB]
---

### Creating a member information table   
// 회원정보 테이블 생성   

```sql
CREATE TABLE DBMIRA.TB_MEMB (
    USR_NO VARCHAR(5) NOT NULL PRIMARY KEY,
    USR_CLS CHAR(1) NOT NULL,
    USR_ID VARCHAR(12) NOT NULL,
    USR_PWD VARCHAR(100) NOT NULL,
    USR_NM VARCHAR(100) NOT NULL,
    HP_DDD_NO VARCHAR(4) NOT NULL,
    HP_NO VARCHAR(8) NOT NULL,
    USR_EMAIL VARCHAR(100),
    ZIP_CD VARCHAR(6) NOT NULL,
    ZIP_ADDR VARCHAR(150) NOT NULL,
    DETAIL_ADDR VARCHAR(150),
    VISIT_DTM CHAR(14),
    VISIT_HOST VARCHAR(15),
    REG_DTM CHAR(14),
    EDT_DTM CHAR(14)
)
ENGINE=INNODB
DEFAULT CHARSET=UTF8MB4
COLLATE=UTF8MB4_GENERAL_CI
```

```sql
ALTER TABLE DBMIRA.TB_MEMB 
MODIFY COLUMN USR_NO VARCHAR(5) CHARACTER SET UTF8MB4 COLLATE UTF8MB4_GENERAL_CI NOT NULL COMMENT '회원고유번호'
```

```sql
ALTER TABLE TB_MEMB 
MODIFY USR_PWD VARCHAR(100) AFTER USR_ID
```

```sql
ALTER TABLE TB_MEMB 
DROP PRIMARY KEY
```

```sql
ALTER TABLE TB_MEMB 
ADD PRIMARY KEY(USR_NO)
```

```sql
ALTER TABLE TB_MEMB 
ADD UNIQUE KEY(USR_ID)
```

### Check the ID and reply to 1 if it's there or 0 if it's not there   
// 아이디 확인해서 있으면 1, 없으면 0 회신   

```sql
SELECT EXISTS (
    SELECT USR_ID 
    FROM TB_MEMB 
    WHERE USR_ID="aaaaaa" 
    LIMIT 1
) AS IDCHECK
```

### Check the ID, Password and reply to 1 if it's there or 0 if it's not there   
// 아이디, 비밀번호 확인해서 있으면 1, 없으면 0 회신   

```sql
SELECT EXISTS (
    SELECT USR_ID 
    FROM TB_MEMB 
    WHERE USR_ID="aaaaaa" 
        AND USR_PWD="11111111!a" 
    LIMIT 1
) AS IDPWDCHECK
```

### Find ID and save the current date, time, host   
// 아이디 찾아서 현재날짜, 시간, 호스트 저장   

```sql
UPDATE TB_MEMB
SET VISIT_DTM = (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
    VISIT_HOST = '111.111.111.111'
WHERE USR_ID = 'iiiddd'
```

### Creating a member information sequence   
// 회원정보 시퀀스 생성   

```sql
CREATE SEQUENCE USR_SEQ
    INCREMENT BY 1
    START WITH 1
    MINVALUE 1
    MAXVALUE 99999
    NOCYCLE
    NOCACHE
```

### Join membership   
// 회원가입   

```sql
INSERT INTO TB_MEMB 
VALUES(
    LPAD(NEXTVAL(USR_SEQ), 5, '0'),
    #{usrCls},
    #{usrNm},
    #{usrId},
    #{usrPwd},
    #{hpDddNo},
    #{hpNo},
    #{usrEmail},
    #{zipCd},
    #{zipAddr},
    #{detailAddr},
    (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
    #{visitHost},
    (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
    ''
)
```

### For the first time testing of seller information   
// 판매자정보 최초 테스트용   

```sql
INSERT INTO TB_MEMB 
VALUES(
    LPAD(NEXTVAL(USR_SEQ), 5, '0'),
    '1',
    '부산점관리자',
    LPAD(NEXTVAL(USR_SEQ), 5, '0'),
    LPAD(NEXTVAL(USR_SEQ), 5, '0'),
    '010',
    '11111111',
    '',
    '11111',
    '주소',
    '',
    (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
    '알 수 없는 IP로 접속',
    (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
    ''
)
```

### Creating a refresh token table   
// 리플레시 토큰 테이블 생성   

```sql
CREATE TABLE DBMIRA.TB_TOKEN (
    ID VARCHAR(12) NOT NULL PRIMARY KEY,
    USR_ID VARCHAR(12) NOT NULL,
    REFRESH_TOKEN VARCHAR(300) NOT NULL
)
ENGINE=INNODB
DEFAULT CHARSET=UTF8MB4
COLLATE=UTF8MB4_GENERAL_CI
```

```sql
ALTER TABLE TB_TOKEN 
ADD UNIQUE KEY(USR_ID)
```

### Create prepaid money table   
// 선불머니원장 테이블 생성   

```sql
CREATE TABLE DBMIRA.TB_MONEY (
    USR_NO VARCHAR(5) NOT NULL,
    MONEY_NO VARCHAR(8) NOT NULL PRIMARY KEY,
    MONEY_BALANCE_SUM VARCHAR(10) NOT NULL,
    REG_DTM CHAR(14),
    EDT_DTM CHAR(14)
)
ENGINE=INNODB
DEFAULT CHARSET=UTF8MB4
COLLATE=UTF8MB4_GENERAL_CI
```

### Create prepaid money sequence   
// 선불머니원장 시퀀스 생성   

```sql
CREATE SEQUENCE MONEY_SEQ
    INCREMENT BY 1
    START WITH 1
    MINVALUE 1
    MAXVALUE 99999
    NOCYCLE
    NOCACHE
```

```sql
ALTER TABLE TB_MONEY 
ADD UNIQUE KEY(USR_NO)
```

### For the first test of prepaid money   
// 선불머니원장 최초 테스트용   

```sql
INSERT INTO TB_MONEY 
VALUES(
    '00007',
    LPAD(NEXTVAL(MONEY_SEQ), 8, '0'),
    '0',
    (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
    ''
)
```

### Create prepaid money history table   
// 선불머니내역 테이블 생성   

```sql
CREATE TABLE DBMIRA.TB_MONEYLIST (
    USR_NO VARCHAR(5) NOT NULL,
    MONEY_NO VARCHAR(8) NOT NULL,
    CHARGE_NO VARCHAR(17) NOT NULL PRIMARY KEY,
    CHARGE_CODE CHAR(1) NOT NULL,
    CHARGE_MONEY VARCHAR(10) NOT NULL,
    MONEY_BALANCE_CURRENT VARCHAR(10) NOT NULL,
    REG_DTM CHAR(14)
)
ENGINE=INNODB
DEFAULT CHARSET=UTF8MB4
COLLATE=UTF8MB4_GENERAL_CI
```

### Create prepaid money history sequence   
// 선불머니내역 시퀀스 생성   

```sql
CREATE SEQUENCE CHARGE_SEQ
    INCREMENT BY 1
    START WITH 1
    MINVALUE 1
    MAXVALUE 99999
    NOCYCLE
    NOCACHE
```

```sql
INSERT INTO TB_MONEYLIST 
VALUES(
    '00050',
    (
        SELECT MONEY_NO
        FROM TB_MONEY
        WHERE USR_NO = '00050'
    ),
    LPAD(NEXTVAL(CHARGE_SEQ), 17, '0'),
    '1',
    '10000',
    (
        (
            SELECT MONEY_BALANCE_SUM
            FROM TB_MONEY
            WHERE USR_NO = '00050'
        ) + '10000'
    ),
    (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s'))
)
```

### Creating a merket table   
// 가맹점 테이블 생성   

```sql
CREATE TABLE DBMIRA.TB_MARKET (
    MARKET_NO VARCHAR(4) NOT NULL PRIMARY KEY,
    MARKET_NM VARCHAR(100) NOT NULL,
    REG_DTM CHAR(14),
    EDT_DTM CHAR(14)
)
ENGINE=INNODB
DEFAULT CHARSET=UTF8MB4
COLLATE=UTF8MB4_GENERAL_CI
```

### Create merket sequence   
// 가맹점 시퀀스 생성   

```sql
CREATE SEQUENCE MARKET_SEQ
    INCREMENT BY 1
    START WITH 1
    MINVALUE 1
    MAXVALUE 99999
    NOCYCLE
    NOCACHE
```

### For merket first test   
// 가맹점 최초 테스트용   

```sql
INSERT INTO TB_MARKET 
VALUES(
    LPAD(NEXTVAL(MARKET_SEQ), 4, '0'),
    '부산점',
    (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
    ''
)
```

### Creating a goods list table   
// 상품목록 테이블 생성   

```sql
CREATE TABLE DBMIRA.TB_GOODS (
    MARKET_NO VARCHAR(4) NOT NULL,
    SELR_USR_NO VARCHAR(5) NOT NULL,
    GDS_NO VARCHAR(17) NOT NULL PRIMARY KEY,
    GDS_SNO VARCHAR(7) NOT NULL,
    GDS_NM VARCHAR(200) NOT NULL,
    GDS_AMT VARCHAR(10),
    GDS_QTT CHAR(8),
    GDS_SELL_QTT CHAR(8),
    GDS_CLS_DT CHAR(8),
    GDS_SHPP_COST VARCHAR(6),
    GDS_DESC VARCHAR(4000),
    GDS_IMG_PATH VARCHAR(200),
    REAL_FILE_NM VARCHAR(100),
    BUY_YN CHAR(1),
    BUY_CNCL_DT CHAR(8),
    CANCEL_YN_DT CHAR(2),
    REG_DTM CHAR(14),
    REG_USR_NO VARCHAR(5),
    EDT_DTM CHAR(14),
    EDT_USR_NO VARCHAR(5)
)
ENGINE=INNODB
DEFAULT CHARSET=UTF8MB4
COLLATE=UTF8MB4_GENERAL_CI
```

### Create a goods list sequence   
// 상품목록 시퀀스 생성   

```sql
CREATE SEQUENCE GDS_SEQ
    INCREMENT BY 1
    START WITH 1
    MINVALUE 1
    MAXVALUE 99999
    NOCYCLE
    NOCACHE
```

### For the first test of goods list   
// 상품목록 최초 테스트용   

```sql
INSERT INTO TB_GOODS 
VALUES(
    '0010',
    '00020',
    LPAD(NEXTVAL(GDS_SEQ), 17, '0'),
    LPAD(NEXTVAL(GDS_SEQ), 7, '0'),
    '슬리퍼20',
    '10000',
    '10',
    '0',
    '',
    '0',
    '상품설명 생략',
    '',
    '',
    'Y',
    '',
    '7',
    (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
    '00020',
    '',
    ''
)
```

```sql
SELECT MARKET_NO,
    GDS_NO,
    GDS_NM,
    GDS_AMT,
    GDS_SHPP_COST,
FROM TB_GOODS
WHERE GDS_QTT > 0
    AND BUY_YN = 'Y'
ORDER BY GDS_NM ASC
```

```sql
UPDATE TB_GOODS
SET GDS_QTT = (GDS_QTT - 1),
    GDS_SELL_QTT = (GDS_SELL_QTT + 1),
    EDT_DTM = (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
    EDT_USR_NO = #{edtUsrNo}
WHERE GDS_NO = #{gdsNo}
    AND MARKET_NO = #{marketNo}
```

### Creating a purchase history table   
// 구매내역 테이블 생성   

```sql
CREATE TABLE DBMIRA.TB_BUYLIST (
    USR_NO VARCHAR(5) NOT NULL,
    MARKET_NO VARCHAR(4) NOT NULL,
    GDS_NO VARCHAR(17) NOT NULL,
    GDS_NM VARCHAR(200) NOT NULL,
    BUY_NO VARCHAR(17) NOT NULL PRIMARY KEY,
    BUY_DT CHAR(8),
    BUY_TM CHAR(6),
    CANCEL_YN_DTM CHAR(14),
    BUY_AMT VARCHAR(15),
    BUY_QTT CHAR(5),
    BUY_SHPP_COST VARCHAR(6),
    BUY_PAYMENT_CODE CHAR(1),
    SELR_MONEY VARCHAR(15),
    BUY_STAT CHAR(1),
    DELIVERY_STAT CHAR(1),
    DELIVERY_NO VARCHAR(15),
    PROC_STAT CHAR(1),
    PROC_DTM CHAR(14)
)
ENGINE=INNODB
DEFAULT CHARSET=UTF8MB4
COLLATE=UTF8MB4_GENERAL_CI
```

### Create purchase history sequence   
// 구매내역 시퀀스 생성   

```sql
CREATE SEQUENCE BUY_SEQ
    INCREMENT BY 1
    START WITH 1
    MINVALUE 1
    MAXVALUE 99999
    NOCYCLE
    NOCACHE
```

```sql
SELECT * 
FROM TB_BUYLIST
WHERE USR_NO='00002'
    AND BUY_DT='20230712'
    AND BUY_PAYMENT_CODE = '1'
```

```sql
EXPLAIN
SELECT * 
FROM TB_BUYLIST
WHERE USR_NO = '00002'
```

### Index generation grammar   
// 인덱스 생성 문법   

```sql
CREATE OR REPLACE INDEX 인덱스명 
ON 테이블명 (컬럼1 [, 컬럼2, 컬럼3, ...])
```

### (e.g.) To create an index in reverse order of the title of the post (BUY_DT) on the bulletin board (TB_BUYLIST)   
// (예제) 게시판 (TB_BUYLIST) 에 게시글제목 (BUY_DT) 의 역순으로 인덱스 생성하는 경우   

```sql
CREATE OR REPLACE INDEX IDX_BUYLIST 
ON TB_BUYLIST (BUY_DT, BUY_NO DESC)
```

```sql
SELECT *
FROM INFORMATION_SCHEMA.STATISTICS
WHERE TABLE_SCHEMA = 'DBNAME'
```

```sql
SELECT MARKET_NO,
    GDS_NM,
    BUY_NO,
    BUY_DT,
    BUY_AMT,
    BUY_SHPP_COST,
    BUY_PAYMENT_CODE,
    BUY_STAT,
    DELIVERY_STAT,
    DELIVERY_NO,
    PROC_STAT
FROM TB_BUYLIST
WHERE DATE(a.BUY_DT) BETWEEN '20230709' AND '20230710'
    AND a.USR_NO = '00002'
    AND BUY_PAYMENT_CODE = 2
ORDER BY BUY_NO DESC
```

```sql
SELECT ROW_NUMBER () OVER(ORDER BY a.BUY_NO DESC) AS LIST_NO,
    b.MARKET_NM AS MARKET_NO,
    a.GDS_NM,
    a.BUY_NO,
    a.BUY_DT,
    a.BUY_AMT,
    a.BUY_SHPP_COST,
    a.BUY_PAYMENT_CODE,
    a.BUY_STAT,
    a.DELIVERY_STAT,
    a.DELIVERY_NO,
    a.PROC_STAT
FROM TB_BUYLIST AS a
INNER JOIN TB_MARKET AS b
ON a.MARKET_NO = b.MARKET_NO
WHERE DATE(a.BUY_DT) BETWEEN '20230709' AND '20230710'
    AND a.USR_NO = '00002'
    AND a.BUY_PAYMENT_CODE = 1
ORDER BY BUY_NO DESC
```
