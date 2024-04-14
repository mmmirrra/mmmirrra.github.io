---
layout: post
title:  "Introduction to Data Analysis: Level of Measurement and Data Type"
date:   2024-03-06 09:00:00 +0900
categories: [Data Analysis]
---

### How to collect data   
// 데이터 수집 방법   
   
// 통계조사, 실험, 관찰 등을 통해서 조사단위나 실험단위로부터 정해진 측정 방법 (측정도구, 질문지) 으로 측정하여 얻음   
// 측정 : 각각의 조사단위의 어떤 특성을 일정한 기준에 따라 관측하여 각 조사단위에 수치를 부여하는 작업   
// - 예시 : 표본으로 뽑힌 사람들의 몸무게, 지능 혹은 취업상태 등을 관측하여 수치로 나타내는 경우   
// → 측정된 전체 자료를 데이터 (data) 라고 함   
- It is obtained by measuring by a designated measurement method from an investigation unit or experimental unit through statistical survey, experiment, observation, etc. (Measurement tool, questionnaire)   
- Measurement : Observing certain characteristics of each survey unit according to certain criteria and assigning numerical values to each survey unit   
  - Example : When the weight, intelligence, or employment status of the sampled people are observed and expressed as figures   
- → The entire data measured is referred to as data   
   
<br />
### Basic Data Terminology   
// 데이터 관련 기본용어   
   
// 케이스 (case, 레코드) : 데이터 세트에서 하나의 조사단위에 대한 정보의 집합체   
// 변수 (variable, 필드) : 각 조사단위로부터 측정된 개별적인 속성   
// - 예시 : 어느 단체에서 10명을 표본으로 추출하여 각 사람으로부터 이름, 성별, 나이, 교육정도, 월수입을 조사하는 경우   
// -- 케이스 1 : [이름 : 홍], [성별 : 남자], [나이 : 30], [교육정도 : 고졸], [월수입 : 200만원]   
// -- 케이스 2 : [이름 : 박], [성별 : 여자], [나이 : 31], [교육정도 : 대졸], [월수입 : 230만원]   
// -- 케이스 3 : [이름 : 임], [성별 : 남자], [나이 : 27], [교육정도 : .], [월수입 : 210만원]   
- case, record : A collection of information about one survey unit in a data set   
- variable, field : Individual properties measured from each unit of investigation   
  - Example : A sample of 10 people from an organization is used to examine each person's name, gender, age, educational level, and monthly income   
    - case 1 : [Name : Hong], [Gender : Male], [Age : 30], [Education : High school graduate] [Monthly income : 2 million won]   
    - case 2 : [Name : Park], [Gender : Female], [Age : 31], [Education : College graduate], [Monthly income : 2.3 million won]   
    - case 3 : [Name : Lim], [Gender : Male], [Age : 27], [Education : .], [Monthly income : 2.1 million won]   
   
Representation of matrix form of data   
// 데이터의 행렬 형태 표현   
   
|Name|Gender|Age|Education|Monthly income|
|:---:|:---:|:---:|:---:|:---:|
|Hong|Male|30|High school graduate|2 million won|
|Park|Female|31|College graduate|2.3 million won|
|Lim|Male|27|.|2.1 million won|
   
// -- 데이터를 행렬 형태로 표시하면 이해하기 쉬움   
// -- 각 행은 케이스 (레코드), 각 열은 변수 (필드) 가 됨   
// -- 임 케이스에서 교육정도의 "."는 결측값을 뜻함   
- Displaying data in matrix form is easy to understand   
- Each row becomes a case (record) and each column becomes a variable (field)   
- In Case Lim, the "." of the degree of education means a missing value   
   
<br />
### level of measurement   
// 측정의 수준   
   
// 측정수준에 따라 명목척도, 순서척도, 구간척도, 비율척도로 구분함   
// 측정의 척도에 따라서 제공되는 정보의 수준과 데이터 분석에 이용할 수 있는 분석 방법이 달라짐   
  - Depending on the level of measurement, it is divided into nominal scale, ordinal scale, interval scale, and ratio scale   
  - The measurement scale varies the level of information provided and the analytical methods available for data analysis   
   
<br />
### nominal scale   
// 명목척도, 명명척도   
   
// 측정대상의 속성을 단순히 분류하거나 확인할 목적으로 수치 부여   
// 단순히 범주 구분이 목적임   
// - 수치의 대소 비교, 연산은 의미가 없음   
// - 예시 : 성별 (남자 (1), 여자 (2)), 운동선수의 등번호, 종교, 지지정당, 거주지 (대도시, 중소도시, 농어촌) 등은 연산의 의미가 없음   
- Give numerical values for the purpose of simply classifying or verifying the properties of a measurement target   
- The purpose is simply to categorize   
  - Comparison of figures, calculations are meaningless   
  - Example : Gender (male (1), female (2)), athlete's uniform number, religion, support party, residence (large cities, small and medium-sized cities, and rural areas) have no meaning in calculations   
   
<br />
### ordinal scale   
// 순서척도, 서열척도   
   
// 어떤 특성을 많고 적음에 따라 수치를 부여함   
// 수치 자체가 어떤 절대적인 수나 양, 크기 등을 나타내지 않고, 서열, 대소 관계의 구분만 의미 있음   
// - 예시 : 제품이나 서비스의 질을 묻는 질문 (아주 좋음 (5), 약간 좋음 (4), 보통 (3), 약간 나쁨 (2), 아주 나쁨 (1))   
- To give a numerical value according to many or few characteristics   
- The figures themselves do not represent any absolute number, amount, size, etc., only the distinction between sequences and relationships is meaningful   
  - Example : a question about the quality of a product or service (very good (5), slightly good (4), usually (3), slightly bad (2), very bad (1))   
   
<br />
### interval scale   
// 구간척도, 등간척도   
   
// 측정대상을 속성에 따라 서열화는 물론 서열간의 간격이 같도록 수치 부여   
// 연속형 값으로 측정값의 차이는 의미 있지만, 비 (比) 는 의미 없음   
// 절대 0을 정의할 수 없고, 임의로 지정된 0만 있음   
// - 예시 : 섭씨온도, IQ, 주가지수, 적성검사 점수 등   
- Sequencing the measurement targets according to their attributes, as well as giving numerical values so that the spacing between the sequences is the same   
- The difference in measurements as continuous values is meaningful, but the ratio is meaningless   
- Absolute zero cannot be defined, only a randomly specified zero   
  - Example : Celsius temperature, IQ, stock index, aptitude test score, etc.   
   
<br />
### ratio scale   
// 비율척도   
   
// 구간척도와 유사하지만 측정값의 차이뿐만 아니라 비 (比) 도 의미 있는 경우   
// 절대 0을 정의할 수 있음   
// - 예시 : 소득, 체중, 신장, 시간, 방문객 수 등   
- Similar to the interval scale, but the ratio as well as the difference in the measurements are meaningful   
- Absolute zero can be defined   
  - Example : income, weight, height, time, number of visitors, etc.   
   
<br />
### data classification   
// 데이터의 구분   
   
// 측정 수준에 따른 구분   
// - 질적변수   
// - 양적변수 : 연속형 변수   
- Classification by measurement level   
  - qualitative variable   
  - quantitative variable : continuous variable   
   
// 측정되는 변수의 수에 따른 구분   
// - 일변량 데이터 : 변수의 수가 1개인 것   
// - 다변량 데이터 : 변수의 수가 2개 이상인 것   
- Classification by the number of variables being measured   
  - Univariate data : one variable   
  - Multivariate data : more than one variable   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
