---
layout: post
title:  "MariaDB: sql"
date:   2023-08-06 09:00:00 +0900
categories: [MariaDB]
---

###  // 회원정보 테이블 생성   
{% highlight react %}
CREATE TABLE dbmira.tb_memb (
USR_NO varchar(5) not null primary key,
USR_CLS char(1) not NULL,
USR_ID varchar(12) not NULL,
USR_PWD varchar(100) not NULL,
USR_NM varchar(100) not NULL,
HP_DDD_NO varchar(4) not NULL,
HP_NO varchar(8) not NULL,
USR_EMAIL varchar(100),
ZIP_CD varchar(6) not NULL,
ZIP_ADDR varchar(150) not NULL,
DETAIL_ADDR varchar(150),
VISIT_DTM char(14),
VISIT_HOST varchar(15),
REG_DTM char(14),
EDT_DTM char(14)
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_general_ci;
{% endhighlight %}

{% highlight react %}
ALTER TABLE dbmira.tb_memb MODIFY COLUMN USR_NO varchar(5) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci NOT NULL COMMENT '회원고유번호';
{% endhighlight %}

{% highlight react %}
ALTER TABLE tb_memb MODIFY USR_PWD varchar(100) AFTER USR_ID;
{% endhighlight %}

{% highlight react %}
ALTER TABLE tb_memb DROP PRIMARY KEY;
{% endhighlight %}

{% highlight react %}
ALTER TABLE tb_memb ADD PRIMARY KEY(USR_NO);
{% endhighlight %}

{% highlight react %}
ALTER TABLE tb_memb ADD UNIQUE KEY(USR_ID);
{% endhighlight %}

###  // 아이디 확인해서 있으면 1, 없으면 0 회신
{% highlight react %}
SELECT EXISTS (SELECT USR_ID FROM tb_memb WHERE USR_ID="aaaaaa" LIMIT 1) AS IDCHECK;
{% endhighlight %}

###  // 아이디, 비밀번호 확인해서 있으면 1, 없으면 0 회신
{% highlight react %}
SELECT EXISTS (SELECT USR_ID FROM tb_memb WHERE USR_ID="aaaaaa" and USR_PWD="11111111!a" LIMIT 1) AS IDPWDCHECK;
{% endhighlight %}

###  // 아이디 찾아서 현재날짜시간과 host 저장
{% highlight react %}
UPDATE tb_memb
SET VISIT_DTM = (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
VISIT_HOST = '111.111.111.111'
WHERE USR_ID = 'mirakim';
{% endhighlight %}

###  // 회원정보 시퀀스 생성
{% highlight react %}
CREATE SEQUENCE usr_seq
INCREMENT BY 1
START WITH 1
MINVALUE 1
MAXVALUE 99999
NOCYCLE
NOCACHE;
{% endhighlight %}

###  // 회원가입
{% highlight react %}
INSERT INTO tb_memb VALUES(
LPAD(NEXTVAL(usr_seq), 5, '0'),
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
);
{% endhighlight %}

###  // 판매자정보 최초 테스트용
{% highlight react %}
INSERT INTO tb_memb VALUES(
LPAD(NEXTVAL(usr_seq), 5, '0'),
'1',
'부산점 점장',
LPAD(NEXTVAL(usr_seq), 5, '0'),
LPAD(NEXTVAL(usr_seq), 5, '0'),
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
);
{% endhighlight %}

{% highlight react %}
SELECT * FROM tb_memb;
{% endhighlight %}

###  // 리플레시 토큰 테이블 생성
{% highlight react %}
CREATE TABLE dbmira.tb_token (
ID varchar(12) not null primary key,
USR_ID varchar(12) not null,
REFRESH_TOKEN varchar(300) not NULL
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_general_ci;
{% endhighlight %}

{% highlight react %}
ALTER TABLE tb_token ADD UNIQUE KEY(USR_ID);
{% endhighlight %}

{% highlight react %}
SELECT * FROM tb_token;
{% endhighlight %}


###  // 선불머니원장 테이블 생성
{% highlight react %}
CREATE TABLE dbmira.tb_money (
USR_NO varchar(5) not null,
MONEY_NO varchar(8) not null primary key,
MONEY_BALANCE_SUM varchar(10) not NULL,
REG_DTM char(14),
EDT_DTM char(14)
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_general_ci;
{% endhighlight %}

###  // 선불머니원장 시퀀스 생성
{% highlight react %}
CREATE SEQUENCE money_seq
INCREMENT BY 1
START WITH 1
MINVALUE 1
MAXVALUE 99999
NOCYCLE
NOCACHE;
{% endhighlight %}

{% highlight react %}
ALTER TABLE tb_money ADD UNIQUE KEY(USR_NO);
{% endhighlight %}

###  // 선불머니원장 최초 테스트용
{% highlight react %}
INSERT INTO tb_money VALUES(
'00007',
LPAD(NEXTVAL(money_seq), 8, '0'),
'0',
(SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
''
);
{% endhighlight %}

{% highlight react %}
SELECT * FROM tb_money;
{% endhighlight %}


###  // 선불머니내역 테이블 생성
{% highlight react %}
CREATE TABLE dbmira.tb_moneylist (
USR_NO varchar(5) not null,
MONEY_NO varchar(8) not null,
CHARGE_NO varchar(17) not null primary key,
CHARGE_CODE char(1) not null,
CHARGE_MONEY varchar(10) not null,
MONEY_BALANCE_CURRENT varchar(10) not null,
REG_DTM char(14)
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_general_ci;
{% endhighlight %}

###  // 선불머니내역 시퀀스 생성
{% highlight react %}
CREATE SEQUENCE charge_seq
INCREMENT BY 1
START WITH 1
MINVALUE 1
MAXVALUE 99999
NOCYCLE
NOCACHE;
{% endhighlight %}

{% highlight react %}
INSERT INTO tb_moneylist VALUES(
'00050',
(SELECT MONEY_NO
FROM tb_money
WHERE USR_NO = '00050'),
LPAD(NEXTVAL(charge_seq), 17, '0'),
'1',
'10000',
((SELECT MONEY_BALANCE_SUM
FROM tb_money
WHERE USR_NO = '00050'
) + '10000'),
(SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s'))
);
{% endhighlight %}

{% highlight react %}
SELECT * FROM tb_moneylist;
{% endhighlight %}


###  // 가맹점 테이블 생성
{% highlight react %}
CREATE TABLE dbmira.tb_market (
MARKET_NO varchar(4) not null primary key,
MARKET_NM varchar(100) not null,
REG_DTM char(14),
EDT_DTM char(14)
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_general_ci;
{% endhighlight %}

###  // 가맹점 시퀀스 생성
{% highlight react %}
CREATE SEQUENCE market_seq
INCREMENT BY 1
START WITH 1
MINVALUE 1
MAXVALUE 99999
NOCYCLE
NOCACHE;
{% endhighlight %}

###  // 가맹점 최초 테스트용
{% highlight react %}
INSERT INTO tb_market VALUES(
LPAD(NEXTVAL(market_seq), 4, '0'),
'부산점',
(SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
''
);
{% endhighlight %}

{% highlight react %}
SELECT MARKET_NO, MARKET_NM
FROM tb_market
{% endhighlight %}

{% highlight react %}
SELECT * FROM tb_market;
{% endhighlight %}



###  // 상품목록 테이블 생성
{% highlight react %}
CREATE TABLE dbmira.tb_goods (
MARKET_NO varchar(4) not null,
SELR_USR_NO varchar(5) not null,
GDS_NO varchar(17) not null primary key,
GDS_SNO varchar(7) not null,
GDS_NM varchar(200) not null,
GDS_AMT varchar(10),
GDS_QTT char(8),
GDS_SELL_QTT char(8),
GDS_CLS_DT char(8),
GDS_SHPP_COST varchar(6),
GDS_DESC varchar(4000),
GDS_IMG_PATH varchar(200),
REAL_FILE_NM varchar(100),
BUY_YN char(1),
BUY_CNCL_DT char(8),
CANCEL_YN_DT char(2),
REG_DTM char(14),
REG_USR_NO varchar(5),
EDT_DTM char(14),
EDT_USR_NO varchar(5)
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_general_ci;
{% endhighlight %}

###  // 상품목록 시퀀스 생성
{% highlight react %}
CREATE SEQUENCE gds_seq
INCREMENT BY 1
START WITH 1
MINVALUE 1
MAXVALUE 99999
NOCYCLE
NOCACHE;
{% endhighlight %}

###  // 상품목록 최초 테스트용
{% highlight react %}
INSERT INTO tb_goods VALUES(
'0010',
'00020',
LPAD(NEXTVAL(gds_seq), 17, '0'),
LPAD(NEXTVAL(gds_seq), 7, '0'),
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
);
{% endhighlight %}

{% highlight react %}
SELECT MARKET_NO,
GDS_NO,
GDS_NM,
GDS_AMT,
GDS_SHPP_COST,
FROM tb_goods
WHERE GDS_QTT > 0
and BUY_YN = 'Y'
ORDER BY GDS_NM asc
{% endhighlight %}

{% highlight react %}
UPDATE tb_goods
SET GDS_QTT = (GDS_QTT - 1),
GDS_SELL_QTT = (GDS_SELL_QTT + 1),
EDT_DTM = (SELECT DATE_FORMAT((SELECT NOW()), '%Y%m%d%H%i%s')),
EDT_USR_NO = #{edtUsrNo}
WHERE GDS_NO = #{gdsNo}
AND MARKET_NO = #{marketNo}
{% endhighlight %}

{% highlight react %}
SELECT * FROM tb_goods;
{% endhighlight %}



###  // 구매내역 테이블 생성
{% highlight react %}
CREATE TABLE dbmira.tb_buylist (
USR_NO varchar(5) not null,
MARKET_NO varchar(4) not null,
GDS_NO varchar(17) not null,
GDS_NM varchar(200) not null,
BUY_NO varchar(17) not null primary key,
BUY_DT char(8),
BUY_TM char(6),
CANCEL_YN_DTM char(14),
BUY_AMT varchar(15),
BUY_QTT char(5),
BUY_SHPP_COST varchar(6),
BUY_PAYMENT_CODE char(1),
SELR_MONEY varchar(15),
BUY_STAT char(1),
DELIVERY_STAT char(1),
DELIVERY_NO varchar(15),
PROC_STAT char(1),
PROC_DTM char(14)
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_general_ci;
{% endhighlight %}


###  // 구매내역 시퀀스 생성
{% highlight react %}
CREATE SEQUENCE buy_seq
INCREMENT BY 1
START WITH 1
MINVALUE 1
MAXVALUE 99999
NOCYCLE
NOCACHE;
{% endhighlight %}


{% highlight react %}
SELECT * FROM tb_buylist
where USR_NO='00002'
and BUY_DT='20230712'
and BUY_PAYMENT_CODE = '1';
{% endhighlight %}

{% highlight react %}
SELECT * FROM tb_buylist;
{% endhighlight %}



{% highlight react %}
EXPLAIN
SELECT * FROM tb_buylist
WHERE USR_NO = '00002';
{% endhighlight %}

###  // 인덱스 생성 문법
{% highlight react %}
CREATE OR REPLACE INDEX 인덱스명 ON 테이블명 (컬럼1 [, 컬럼2, 컬럼3, ...])
{% endhighlight %}

###  // 예제: 게시판(tb_buylist)에 게시글제목(BUY_DT)의 역순으로 인덱스 생성하는 경우
{% highlight react %}
CREATE OR REPLACE INDEX IDX_BUYLIST ON tb_buylist (BUY_DT, BUY_NO DESC)
{% endhighlight %}

{% highlight react %}
SELECT *
FROM INFORMATION_SCHEMA.STATISTICS
WHERE TABLE_SCHEMA = 'dbmira';
{% endhighlight %}


{% highlight react %}
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
FROM tb_buylist
WHERE DATE(a.BUY_DT) BETWEEN '20230709' AND '20230710'
and a.USR_NO = '00002'
and BUY_PAYMENT_CODE = 2
ORDER BY BUY_NO DESC
{% endhighlight %}

{% highlight react %}
SELECT
row_number () over(order by a.BUY_NO DESC) as LIST_NO,
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
FROM tb_buylist AS a
INNER JOIN tb_market AS b
ON a.MARKET_NO = b.MARKET_NO
WHERE DATE(a.BUY_DT) BETWEEN '20230709' AND '20230710'
and a.USR_NO = '00002'
and a.BUY_PAYMENT_CODE = 1
ORDER BY BUY_NO DESC
{% endhighlight %}
