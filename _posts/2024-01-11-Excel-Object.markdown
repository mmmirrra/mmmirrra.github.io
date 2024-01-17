---
layout: post
title:  "Excel: What is Object?"
date:   2024-01-11 09:00:00 +0900
categories: [Excel]
---

#### Object structure   
   
// 큰 범위의 오브젝트 -->> 작은 범위의 오브젝트로 구성됨   
Large range of Object -->>> Small range of Object   
`Excel Object > Workbook Object > Sheet Object > Cell Object > row, col (Objects by each range)`   
   
<br />
#### Using Object   
   
// 셀은 디폴트 비활성화 상태임. 셀이 선택되면 active로 상태가 변함   
- Cell is disabled by default. When a cell is selected, the state changes to active.   
   
// 셀을 여러개 선택하면 range를 사용할 수 있음   
- Multiple cells can be selected to use range   
  // ex) range("1").Select 라고 하면 해당 셀의 위치로 이동   
  ex) Type `range("1").Select` to move to the location of the cell   
