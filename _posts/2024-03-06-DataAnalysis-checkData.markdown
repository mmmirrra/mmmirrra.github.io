---
layout: post
title:  "Introduction to Data Analysis: Check the Data Entered"
date:   2024-03-06 09:00:00 +0900
categories: [Data Analysis]
---

### debugging   
// 디버깅   
   
// 입력오류나 또는 조사상 실수로 인한 오류(bug)를 찾아 수정할 목적으로 데이터 세트를 검토하고 분석하는 것   
- Reviewing and analyzing data sets for the purpose of finding and correcting errors caused by input errors or investigative errors   
   
### Check data input errors (if data is large)   
// 데이터 입력 오류 점검(데이터가 큰 경우)   
   
// 각 변수의 입력 범위를 확인하는 방법   
// 변수들간의 논리적 일관성 여부를 확인하는 방법   
- To check the input range of each variable   
- To check for logical consistency between variables   
   
### To check the input range of each variable   
// 각 변수의 입력 범위를 확인하는 방법   
   
// 예시   
// - 응답자의 성별을 나타내는 변수에 대해서 남자(1), 여자(2)로 나타낸 경우   
// - → 변수 값이 1보다 작거나 2보다 큰 경우가 있다면 입력 과정상의 오류이거나 응답자의 잘못된 응답 또는 조사원의 실수로 발생하였다고 볼 수 있음   
- Example   
  - When a variable representing the gender of the respondent is expressed as male (1) and female (2)   
  - → If the variable value is less than 1 or greater than 2, it can be considered an error in the input process or an incorrect response from the respondent or a mistake from the investigator   
   
### To check for logical consistency between variables   
// 변수들간의 논리적 일관성 여부를 확인하는 방법   
   
Example : Create a cross-table between the patient's gender and the type of cancer   
// 예시 : 환자의 성별과 암의 종류간에 교차표 작성   
   
|gender|stomach cancer|lung cancer|breast cancer|uterine cancer|others|total|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|male(1)|8|12|0|3|4|27|
|female(2)|5|3|9|7|2|26|
   
// - 남자는 자궁암이 발생할 수 없음에도 불구하고, 3명의 환자가 자궁암으로 입원하였음   
// -- → 해당 케이스의 관측값을 확인하여 환자 성별이나 암 종류에 대한 입력오류 여부 확인   
  - Three patients were hospitalized for uterine cancer, even though the man could not develop uterine cancer   
    - → Check the case's observations for input errors for patient gender or cancer type   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
