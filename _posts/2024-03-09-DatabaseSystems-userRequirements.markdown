---
layout: post
title:  "Database Systems: Analysis of User Requirements"
date:   2024-03-09 09:00:00 +0900
categories: [Database Systems]
---

### Why analysis of user requirements is necessary   
// 사용자 요구사항 분석의 필요   
   
// 데이터에 대한 충분한 사전 분석없이 적절한 설계가 불가능   
// - 데이터베이스의 구조가 점차 복잡해지고 수명 주기가 단축되기 때문에 신속, 정확성이 요구됨   
// - 데이터베이스의 활용 범위가 확대됨에 따라서 데이터베이스의 효율적인 운용에 초점을 둠   
- Unable to properly design without sufficient pre-analysis of data   
  - Rapidity and accuracy are required as database structures become increasingly complex and life cycles are shortened   
  - Focus on efficient database operation as database utilization grows   
   
// 사용자의 요구를 명세하지 않고 데이터베이스 설계 및 개발을 진행하는 경우   
// - 결과물의 완성도 저하 및 신뢰도 추락함   
// - 개발 후 발생하는 에러 수정에 많은 추가 비용이 지출됨   
- When designing and developing a database without specifying the user's needs
  - Results are less complete and less reliable   
  - High additional costs are spent to correct errors that occur after development   
   
### Concept of user requirement analysis   
// 사용자 요구사항 분석의 개념   
   
// 시스템의 대상이 되는 업무를 분석   
// - 정보 시스템의 데이터베이스가 신속하고 효과적으로 업무 처리를 지원   
// - 필요한 데이터를 저장 및 운용할 수 있는 구조 개발   
- Analyzing the tasks targeted by the system   
  - Database of information systems helps you handle business quickly and effectively   
  - Developing a structure that can store and operate the required data   
   
// 도출, 분석, 기록 단계로 수행   
// - 국제 표준화 : IEEE-Std-830   
- Take steps to derive, analyze, and record   
  - International standardization : IEEE-Std-830   
   
### User Requirements Analysis Process   
// 사용자 요구사항 분석 과정   
   
// 제안요청서 → [요구사항 도출] → 요구사항 명세서 → [요구사항 분석] → 요구사항 정의서 → [요구사항 기록]   
- RFP (Request for Proposer) → [Requirements Derived] → Requirements Statement → [Requirements Analysis] → Requirements Definitions → [Requirements Recorded]   
   
#### Derivation of requirements   
// 요구사항 도출   
   
// 구축대상, 프로젝트 목표, 범위를 기준으로 조사범위를 결정   
// 업무관계자 인터뷰   
// 외부자료 수집 및 분석   
- Determine the scope of the survey based on the target, project objectives, and scope of the project   
- Interview with business officials   
- Collecting and analyzing external data   
   
#### Requirement Analysis   
// 요구사항 분석   
   
// 도출된 요구사항의 명확성, 완전성, 모호성 검증   
// 불완전한 부분이 존재할 경우 요구사항 도출단계 재수행   
// 요구사항을 분류하여 통합 또는 분리   
- Validation of clarity, completeness, and ambiguity of the derived requirements   
- Re-perform the requirement derivation step if incomplete is present   
- Consolidate or separate requirements by categorizing them   
   
#### Requirement Record   
// 요구사항 기록   
   
// 요구사항 목록 정리 및 관리자의 승인   
// 정리된 요구사항을 형식에 맞춰 문서화   
// 프로젝트 종료 때까지 반영 여부 지속적 관리   
- Organize a list of requirements and approve the administrator   
- Document organized requirements in a format   
- Continuous management of reflection until the end of the project   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
