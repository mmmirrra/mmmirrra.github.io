---
layout: post
title:  "DBeaver: How to open a new Script Editor and enter a command"
date:   2024-01-16 09:00:00 +0900
categories: [DBeaver]
---

#### Press `Ctrl + ]` to open a new Script Editor   
// 'Ctrl + ]' 키를 눌러서 Script 편집기 새로 열기   
   
// 'Ctrl + ]' 키를 여러 번 눌러서 여러 개의 Script 편집기를 열 수 있음   
// Script 편집기에서 쿼리를 입력하면 됨   
// 쿼리를 실행할 테이블은 왼쪽의 테이블 트리에서 찾아서 확인할 수 있음   
   
Multiple Script editors can be opened by pressing 'Ctrl + ]' multiple times   
You can enter a query in the Script Editor   
The table to run the query can be found in the table tree on the left   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/DBeaverScript1.png)
   
<br>
#### How to run a query   
// 쿼리를 실행하는 방법   
   
// 'SELECT * FROM' 테이블명 입력 후 문장 위에 커서를 둔 상태로 'Ctrl + Enter' 키를 누르면 쿼리가 실행되어 전체 테이블 목록을 볼 수 있음   
// 여러 줄의 쿼리를 입력한 후 일부 쿼리만 실행하려면 해당 부분만 블럭으로 선택한 후 'Ctrl + Enter' 키를 누름   
   
After entering the 'SELECT * FROM' table name, press 'Ctrl + Enter' with the cursor over the sentence to run the query and view the full table list   
To enter multiple lines of queries and then run only some queries, select them as blocks and press 'Ctrl + Enter'   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/DBeaverScript2.png)
   
// 테이블 속성 중 검색할 속성을 'WHERE'로 추가하여 실행하면 아래 결과창에 검색 결과 출력됨   
If you add and execute an attribute to be searched among table properties via 'WHERE', the search results will be displayed in the results window below   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/DBeaverScript3.png)
   
// 업데이트할 값이 있는 경우 'UPDATE'로 추가하여 실행하면 수정됨   
If there is a value to update, it will be modified by adding and running it through 'UPDATE'   
   
// 왼쪽의 테이블 트리에서 테이블을 직접 열어서 수정하는 것은 혹시 모를 에러를 방지하기 위해 사용을 지양함   
Opening and correcting the table directly in the table tree on the left can lead to a possible error. Avoid using it to prevent errors   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/DBeaverScript4.png)
