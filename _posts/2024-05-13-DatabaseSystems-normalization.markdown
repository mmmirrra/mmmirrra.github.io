---
layout: post
title:  "Database Systems: Normalization"
date:   2024-05-13 09:00:00 +0900
categories: [Database Systems]
---

### Normalization   
// 정규화   
   
<br />
### Good relation and Bad relation   
// 좋은 릴레이션과 나쁜 릴레이션   
   
#### Invalid database modeling   
// 잘못된 데이터베이스 모델링   
   
// 데이터의 중복   
// - 일관성 유지의 어려움   
// - 저장 공간 낭비   
// 갱신 이상   
// - 삽입 이상 : 레코드 추가 시 불필요한 컬럼의 값이 없이는 추가하지 못하는 경우   
// - 삭제 이상 : 삭제 시 의도하지 않았던 다른 데이터가 삭제되는 경우   
// - 수정 이상 : 중복 저장된 레코드를 수정 시 모두 반영이 안되어 데이터베이스의 일관성이 깨지는 경우   
- Data duplication   
  - Difficulty in maintaining consistency   
  - Waste of storage space   
- Renewal abnormalities   
  - Insertion abnormality : When adding records, you cannot add them without unnecessary column values   
  - Delete abnormality : When deleting, other unintended data is deleted   
  - Modified abnormality : Modification of duplicate stored records fails to reflect all and results in database consistency   
   
#### Concept of the good relation   
// 좋은 릴레이션의 개념   
   
// 컴퓨터 프로그래머적 관점에서의 모델링   
// - 어떻게 데이터를 저장해야 하는가?   
// 릴레이션의 스키마가 얼마나 효율적으로 실세계를 반영하고 있는지 평가   
// 고려사항   
// - 한 릴레이션 내의 컬럼 간의 관계 분석   
// - 원하지 않는 데이터의 종속과 중복 제거   
// - 새로운 컬럼들이 데이터베이스에 추가될 때, 기존 컬럼과의 관계 수정을 최소화   
- Computer programmer's perspective of modeling   
  - How do I store my data?   
- Evaluate how efficiently the relation's schema reflects the real world   
- Consideration   
  - Analyzing the relation between columns within a relation   
  - Dependency and deduplication of unwanted data   
  - Minimize the modification of the relation with the existing column when new columns are added to the database   
   
<br />
### Functional Dependency (FD)   
// 함수적 종속성 (FD)   
   
#### Definition of the functional dependency   
// 함수적 종속성의 정의   
   
// 릴레이션 인스턴스를 분석하여 속성들 간의 연관관계를 표현한 것   
// 릴레이션의 효율성을 향상시켜 좋은 릴레이션으로 변환하는데 이용되는 중요한 개념   
- Analyzing a relation instance to express the association between properties   
- An important concept used to improve the efficiency of a relation and convert it into a good one   
   
// 정의   
// ∴ 임의의 릴레이션 스키마 R의 인스턴스 r(R) 에 포함되는 서로 다른 두 레코드 r₁, r₂ 와 컬럼 집합 X 와 Y 에 대해, r₁[X] = r₂[X] 일 때, r₁[y] = r₂[y] 이면 함수적 종속성 X → Y 가 성립한다   
- Definition   
∴ For two different records 'r₁, r₂' and 'column sets X and Y' in 'instance r(R) of any relation schema R', a functional dependency 'X → Y' is established when 'r₁[X] = r₂[X]' is 'r₁[y] = r₂[y]'   
   
#### Discrimination of functional dependency   
// 함수적 종속성의 판별   
   
- Example   
   
|// 고객번호<br />Customer number|// 고객명<br />Customer name|// 전화번호<br />Phone number|// 등급<br />Rating|// 할인율<br />discount rate|
|:---:|:---:|:---:|:---:|:---:|
|C1|Yu Gwan-sun|O1O-OOOO-OOOO|GOLD|5%|
|C2|Son Byung-hee|O1O-OOOO-OOO1|VIP|10%|
|C3|Ji Cheng-cheon|O1O-OOOO-OOO2|VIP|10%|
|C4|Ahn Chang-ho|O1O-OOOO-OOO3|GOLD|5%|
|C5|Ahn Jung-geun|O1O-OOOO-OOO4|VIP|10%|
|C6|Yun Bong-gil|O1O-OOOO-OOO5|NEW|3%|
   
// 표기형식 : `{등급} → {할인율}`   
// - `{등급}` 은 결정자   
// - `{할인율}` 은 종속자   
- Written format : `{Rating} → {discount rate}`   
  - `{Rating}` is the determinant   
  - `{discount rate}` is a dependency   
   
#### Extensions of functional dependency   
// 함수적 종속성의 확장   
   
// 함수적 종속성은 릴레이션의 효율성 여부에 중요한 판단기준임   
// 그러나 릴레이션의 인스턴스만으로 내재된 모든 함수적 종속성을 찾아내기 어려움   
// 판별되지 않은 모든 함수적 종속성을 찾기 위해 추론 규칙을 사용하여 함수적 종속성을 확장   
// 클로저 (closure)   
// - 판별된 함수적 종속성 집합으로부터 유추할 수 있는 모든 함수적 종속성 집합 F<sup>+</sup>   
- Functional dependency is an important criterion for determining the effectiveness of the relation   
- However, it is difficult to find all the inherent functional dependencies from instances of the relation alone   
- To find all undiscriminated functional dependencies, we extend the functional dependencies using inference rules   
- Closure   
  - All functional dependencies sets F<sup>+</sup> that can be inferred from the determined set of functional dependencies   
   
#### Function Dependency Inference Rule   
// 함수적 종속성 추론 규칙   
   
// 암스트롱 공리 (Armstrong's axiom)   
// - 재귀성 규칙 : X ⊇ Y 이면, X → Y 이다   
// - 부가성 규칙 : X → Y 이면, XZ → YZ 이다   
// - 이행성 규칙 : X → Y 이고, Y → Z 이면, X → Z 이다   
// 암스트롱 공리의 확장 버전   
// - 분해 규칙 : X → YZ 이면, X → Y 이고 X → Z 이다   
// - 합집합 규칙 : X → Y 이고, X → Z 이면, X → YZ 이다   
// - 의사 이행성 규칙 : X → Y 이고, WY → Z 이면, WX → Z 이다   
- Armstrong's axiom   
  - Relexive rule : If X ⊇ Y, then X → Y   
  - Augmentation rule : If X → Y, then XZ → YZ   
  - Transitivity rule : If X → Y and Y → Z, then X → Z   
- An extended version of the Armstrong's axiom   
  - Decomposition rule : If X → YZ, then X → Y and X → Z   
  - Union set rule : If X → Y and X → Z, then X → YZ   
  - Pseudo-transitivity rule : If X → Y and WY → Z, then WX → Z   
   
#### Canoical cover ( F<sup>c</sup> )   
// 카노니컬 커버 ( F<sup>c</sup> )   
   
// 함수적 종속성 추론 규칙으로 확장된 클로저에는 자명한 종속성과 중복된 종속성을 포함   
// - 자명한 종속성 : A → A 의미가 당연   
// - 중복된 종속성 : X → AB, X → B 의미가 여러번 존재   
// 불필요한 함수적 종속성을 제거한 표준형으로 변환 후 정규화를 수행   
// 표준형 조건   
// - F의 모든 함수적 종속성의 오른편 속성은 반드시 1개   
// - F에서 X → A를 X의 진부분집합 Y에 대하여 Y → A로 교체했을 때, 그 집합이 F와 동등한 집합이 불가능   
// - F에서 어떤 함수적 종속성을 제거했을 때, 그 집합이 F와 동등한 집합이 불가능   
- Closure extended to functional dependency inference rules include self-evident dependencies and duplicate dependencies   
  - Self-evident dependency : The meaning of 'A → A' is obvious   
  - Duplicate dependencies : X → AB and X → B exist many times   
- Normalization is performed after conversion to a standard form that removes unnecessary functional dependencies   
- Standard form conditions   
  - The right-hand property of all functional dependencies of F must be one   
  - When 'X → A' is replaced by 'Y → A' for the true subset Y of X in F, it is impossible that the set is equivalent to F   
  - When we remove any functional dependencies from F, it is impossible that the set is equivalent to F   
   
#### Functional Dependency Diagram (FDD)   
// 함수적 종속성 다이어그램 (FDD)   
   
// 릴레이션 내의 속성간의 종속 관계를 직관적이고 이해하기 쉽게 도식화한 표현 방식   
// - 직사각형 : 속성 또는 속성 집합   
// - 화살표 : 함수적 종속성   
- Intuitive and easy-to-understand representation of dependent relation between properties within a relation   
  - Rectangle : Property or set of properties   
  - Arrow : Functional Dependencies   
   
- Example   
   
|// 도크번호<br />Dock number|// 입항시간<br />Port of entry time|// 출항시간<br />Time of departure|// 목적<br />Purpose|// 도크관리자<br />Dock manager|// 담당도선사<br />Pilot|
|:---:|:---:|:---:|:---:|:---:|:---:|
|D1|09:00|10:15|Shipping|Kim Gyu-sik|Kim Soon-Ae|
|D1|11:00|11:45|Shipping|Kim Gyu-sik|Kim Soon-Ae|
|D1|11:50|12:45|Unload|Kim Gyu-sik|Kim Gu|
|D2|09:00|10:00|Tour|Han Yong-un|Lee Dong-Hwi|
|D2|12:00|12:45|Refuel|Han Yong-un|Lee Dong-Hwi|
|D2|13:00|15:00|Maintenance|Han Yong-un|Yun Bong-gil|
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/databaseSystemsJoinFunctionDependencyDiagram1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/databaseSystemsJoinFunctionDependencyDiagram2.png)
   
<br />
### Normalization   
// 정규화   
   
#### Concept of Normal Form   
// 정규형의 개념   
   
// 이상현상을 최소화 하도록 특정 조건을 갖춘 릴레이션의 형식   
- Type of relation with certain conditions to minimize anomalies   
   
// 정규형의 분류   
// - 제1정규형 > 제2정규형 > 제3정규형 > 제4정규형 > 제5정규형   
- Classification of Normal Form   
  - 1NF (The first normal form) > 2NF (The second normal form) > 3NF (The third normal form) > 4NF (The fourth normal form) > 5NF (The fifth normal form) or PJNF(projection–join normal form)   
   
#### Purpose of normalization   
// 정규화의 목적   
   
// 정의   
// ∴ 특정 정규형의 조건을 만족하도록 릴레이션과 속성을 재구성하는 과정   
- Definition   
∴ The process of reconstructing relation and properties to satisfy the conditions of a particular normal form   
   
#### Functionality of Normalization   
// 정규화의 기능   
   
// 데이터베이스 내에 모든 릴레이션을 효과적으로 표현   
// 보다 간단한 관계 연산에 기초하여 검색 알고리즘을 효과적으로 작성할 수 있도록 지원   
// 바람직하지 않은 삽입, 수정, 삭제 등의 이상 발생 방지   
// 새로운 형태의 데이터가 삽입될 때 릴레이션 재구성의 필요성을 축소   
- Effective representation of all relations within the database   
- It helps to effectively write search algorithms based on simpler relation operations   
- Prevents undesirable insertion, modification, deletion, etc.   
- It reduces the need for relation reconstruction when new forms of data are inserted   
   
#### The first normal form   
// 제1정규화, 제1정규형   
   
// 가장 조건이 단순한 정규형   
// 관계형 모델에 조건에 따라 자동 적용되는 정규형   
- Normal form with the simplest conditions   
- Normal form automatically applied to relational models based on conditions   
   
// 정의   
// ∴ 릴레이션 스키마에서 정의된 모든 속성의 도메인이 원자값을 갖는 상태   
- Definition   
∴ The state in which the domain of all properties defined in the relation schema has atomic values   
   
#### The second normal form   
// 제2정규화, 제2정규형   
   
// 릴레이션이 제1정규형을 만족하고, 기본키의 부분집합이 특정 속성을 종속하고 있지 않은 상태   
- The relation satisfies the first first normal form, and the subset of the elementary keys does not depend on a particular property   
   
// 정의   
// ∴ 주어진 릴레이션의 인스턴스가 기본키가 아닌 속성들이 기본키에 완전히 종속되어 있는 상태   
- Definition   
∴ A state in which non-elementary key properties of an instance of a given relation are completely dependent on the elementary key   
   
// 기본키에 완전히 종속되도록 릴레이션을 분해   
- Decompose the relation to be completely dependent on the elementary key   
   
#### Lossless decomposition of relation   
// 릴레이션의 무손실 분해 (lossless decomposition)   
   
// 정의   
// ∴ 스키마 R에 함수적 종속성 X → Y 가 존재하고 X ∩ Y = <i>Φ</i> 이면, R 을 R-Y 와 XY로 분해   
- Definition   
∴ If the functional dependency 'X → Y' exists in schema R and 'X ∩ Y = <i>Φ</i>', R is decomposed into 'R-Y' and 'XY'   
   
// 예시   
// - 도크관리 릴레이션 무손실 분해   
// -- {도크번호} → {도크관리자}   
// -- {도크번호} ∩ {도크관리자} = 0   
// `도크관리 - {도크관리자}, {도크번호, 도크관리자}`   
- Example   
  - Lossless decomposition of dock management relation   
    - {Dock number} → {Dock manager}   
    - {Dock number} ∩ {Dock manager} = 0   
  - `Dock management - {Dock manager}, {Dock number, Dock manager}`   
   
// 도크관리 릴레이션   
- Dock management relation   
   
|// 도크번호<br />Dock number|// 입항시간<br />Port of entry time|// 출항시간<br />Time of departure|// 목적<br />Purpose|// 담당도선사<br />Pilot|
|:---:|:---:|:---:|:---:|:---:|
|D1|09:00|10:15|Shipping|Kim Soon-Ae|
|D1|11:00|11:45|Shipping|Kim Soon-Ae|
|D1|11:50|12:45|Unload|Kim Gu|
|D2|09:00|10:00|Tour|Lee Dong-Hwi|
|D2|12:00|12:45|Refuel|Lee Dong-Hwi|
|D2|13:00|15:00|Maintenance|Yun Bong-gil|
   
// 관리자 릴레이션   
- Administrator relation   
   
|// 도크번호<br />Dock number|// 도크관리자<br />Dock manager|
|:---:|:---:|
|D1|Kim Gyu-sik|
|D2|Han Yong-un|
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/databaseSystemsJoinFunctionDependencyDiagram3.png)
   
#### The third normal form   
// 제3정규화, 제3정규형   
   
// 정의   
// ∴ 릴레이션이 제2정규형을 만족하고, 기본키가 아닌 속성들이 어떤 키에도 이행적으로 종속되지 않은 상태   
- Definition   
∴ A state in which the relation satisfies the second normal form and propertes other than the elementary key are not transitionally dependent on any key   
   
// 이행적 종속성   
// - X → Y 이고 Y → Z 이면 X → Z 이다   
- Transitional dependency   
  - If X → Y and Y → Z, then X → Z   
   
- Example   
   
```
// {도크번호, 입항시간} → {목적}
//                       {목적} → {담당도선사}
// {도크번호, 입항시간} → {담당도선사}
{Dock number, Port of entry time} → {Purpose}
                                    {Purpose} → {Pilot}
{Dock number, Port of entry time} → {Pilot}
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/databaseSystemsJoinFunctionDependencyDiagram4.png)
   
// 입출항관리 릴레이션   
- Entry/Exit management relation   
   
|// 도크번호<br />Dock number|// 입항시간<br />Port of entry time|// 출항시간<br />Time of departure|// 목적<br />Purpose|
|:---:|:---:|:---:|:---:|
|D1|09:00|10:15|Shipping|
|D1|11:00|11:45|Shipping|
|D1|11:50|12:45|Unload|
|D2|09:00|10:00|Tour|
|D2|12:00|12:45|Refuel|
|D2|13:00|15:00|Maintenance|
   
// 관리자 릴레이션   
- Administrator relation   
   
|// 도크번호<br />Dock number|// 도크관리자<br />Dock manager|
|:---:|:---:|
|D1|Kim Gyu-sik|
|D2|Han Yong-un|
   
// 도선 릴레이션   
- Lead relation   
   
|// 목적<br />Purpose|// 담당도선사<br />Pilot|
|:---:|:---:|
|Shipping|Kim Soon-Ae|
|Unload|Kim Gu|
|Tour|Lee Dong-Hwi|
|Refuel|Lee Dong-Hwi|
|Maintenance|Yun Bong-gil|
   
#### BC normal form (BCNF)   
// BC정규형 (보이스-코드 정규형(BCNF))   
   
// 정의   
// ∴ 릴레이션이 제3정규형을 만족하고, 릴레이션에 성립하는 X → Y 형태의 모든 함수적 종속성에 대하여 X가 수퍼키인 상태   
- Definition   
∴ A state in which the relation satisfies the third normal form. And A state in which X is super key for all functional dependencies in the form of X → Y established in the relation   
   
- Example   
   
// 입출항관리 릴레이션의 함수적 종속성   
// - {도크번호, 입항시간} → {목적}   
// - {도크번호, 입항시간} → {출항시간}   
// - {목적} → {도크번호}   
- Functional dependency of entry/exit management relation   
  - {Dock number, Port of entry time} → {Purpose}   
  - {Dock number, Port of entry time} → {Time of departure}   
  - {Purpose} → {Dock number}   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/databaseSystemsJoinFunctionDependencyDiagram5.png)
   
// 도크스케줄 릴레이션   
- Dock schedule relation   
   
|// 목적<br />Purpose|// 입항시간<br />Port of entry time|// 출항시간<br />Time of departure|
|:---:|:---:|:---:|
|Shipping|09:00|10:15|
|Shipping|11:00|11:45|
|Unload|11:50|12:45|
|Tour|09:00|10:00|
|Refuel|12:00|12:45|
|Maintenance|13:00|15:00|
   
// 관리자 릴레이션   
- Administrator relation   
   
|// 도크번호<br />Dock number|// 도크관리자<br />Dock manager|
|:---:|:---:|
|D1|Kim Gyu-sik|
|D2|Han Yong-un|
   
// 도선 릴레이션   
- Lead relation   
   
|// 목적<br />Purpose|// 담당도선사<br />Pilot|
|:---:|:---:|
|Shipping|Kim Soon-Ae|
|Unload|Kim Gu|
|Tour|Lee Dong-Hwi|
|Refuel|Lee Dong-Hwi|
|Maintenance|Yun Bong-gil|
   
// 도크 릴레이션   
- Dock relation   
   
|// 목적<br />Purpose|// 도크번호<br />Dock number|
|:---:|:---:|
|Shipping|D1|
|Unload|D1|
|Tour|D2|
|Refuel|D2|
|Maintenance|D2|
   
<br />
### Concept of denormalization   
// 역정규화의 개념   
   
// 정규화   
// - 릴레이션 분할을 통해 데이터의 중복성을 최소화하는 과정   
// - 사용 과정에서 많은 조인 연산을 유발   
// 역정규화   
// - 정규화의 반대 과정   
// - 정규화를 통해 분리되었던 릴레이션을 통합하는 재조정을 수행하고 정보의 부분적 중복을 허용하는 기법   
// - 데이터 접근 성능 개선 목적   
// 정규화되지 않은 스키마와 역정규화 스키마는 구별됨   
- Normalization   
  - Process of minimizing data redundancy through relation segmentation   
  - Invoke many join operations during use   
- Denormalization   
  - The opposite process of normalization   
  - A technique that performs readjustment that integrates relations that have been separated through normalization and allows partial duplication of information   
  - The purpose is to improve data access performance   
- Unnormalized schema and denormalization schema are distinguished   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
