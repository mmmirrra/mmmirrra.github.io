---
layout: post
title:  "Introduction to Data Analysis: Data Input Process"
date:   2024-03-07 09:00:00 +0900
categories: [Data Analysis]
---

### coding   
// 부호화 (코딩)   
   
// 수집된 설문지의 응답결과나 관측결과 등을 통계적 분석이 가능하도록 일정한 원칙에 따라 각 응답에 숫자를 부여하는 과정   
// 연속형 변수는 관측된 값이 숫자이기 때문에 그대로 입력 가능   
// 여러 사람이 부호화 작업에 참여할 때는 부호화의 일관성이 유지되도록 부호화 지침서 (code book) 를 만들어 사용함   
- The process of assigning a number to each response according to a certain principle to enable statistical analysis of the response results or observations of the collected questionnaires   
- Continuous variables can be entered as they are because the observed values are numbers   
- When multiple people participate in encoding, they create and use code book to ensure the consistency of encoding   
   
<br />
### data coding design   
// 데이터 코딩 설계   
   
// 조사/실험을 통해서 얻은 데이터를 입력할 때 어떻게 입력해야 더 간편하고, 효과적으로 분석할 수 있는지를 구상하는 것   
- Envisioning how to input data obtained from research/experiment in a simpler and more effective way to analyze it   
   
<br />
### Example of coding designs for data   
// 데이터에 대한 코딩 설계의 예시   
   
#### A case of conducting a sample survey to examine the impact of the local government system on regional development   
// 지방자치제도가 지역발전에 미친 영향을 살펴보기 위해서 표본 조사를 실시하는 사례   
   
// 설문지 예시   
// - 1. 지방자치제도가 지역 발전에 도움을 준다고 생각하십니까?( ) (순서척도)   
// -- ① 많은 도움을 준다   
// -- ② 조금 도움을 준다   
// -- ③ 별 도움을 주지 못한다   
// -- ④ 전혀 도움을 주지 못한다   
// - 2. 지방자치제가 실시된 이후 지역 간의 경제 불균형에 대해 어떻게 생각하십니까?( ) (명목척도)   
// -- ① 지역간 경제 불균형이 해소되고 있다   
// -- ② 과거와 별 차이 없다   
// -- ③ 지역 간의 불균형이 심화되고 있다   
// -- ④ 잘 모르겠다   
// - 3. 당신의 성별은?( ) (명목척도)   
// -- ① 남자   
// -- ② 여자   
// - 4. 당신의 나이는 몇 세이십니까?( ) (순서척도)   
// -- ① 20세 미만   
// -- ② 20~29세   
// -- ③ 30~39세   
// -- ④ 40~49세   
// -- ⑤ 50~59세   
// -- ⑥ 60세 이상   
// - 5. 당신의 현재 거주지는 어디입니까?( ) (명목척도)   
// -- ① 서울시   
// -- ② 광역시   
// -- ③ 경기/강원   
// -- ④ 충북/충남   
// -- ⑤ 경북/경남   
// -- ⑥ 전북/전남   
// -- ⑦ 제주   
- Questionnaire Example   
  1. Do you think the local government system helps develop the region?( ) (ordinal scale)   
    ① help a lot   
    ② give a little help   
    ③ be of little help   
    ④ be of no help at all   
  2. What do you think of the economic imbalance between regions since the local autonomy system was implemented?( ) (nominal scale)   
    ① The economic imbalance between regions is being resolved   
    ② not much different from the past   
    ③ The imbalance between regions is deepening   
    ④ I don't know   
  3. What's your gender?( ) (nominal scale)   
    ① Male   
    ② Female   
  4. How old are you?( ) (ordinal scale)   
    ① under the age of 20   
    ② 20 to 29 years old   
    ③ 30 to 39 years old   
    ④ 40 to 49 years old   
    ⑤ 50 to 59 years old   
    ⑥ 60 years of age or older   
  5. What is your current residence?( ) (nominal scale)   
    ① Seoul Metropolitan Government   
    ② Metropolitan City   
    ③ Gyeonggi/Gangwon   
    ④ Chungbuk/Chungnam   
    ⑤ North Gyeongsang/South Gyeongsang Province   
    ⑥ Jeonbuk/Jeonnam   
    ⑦ Jeju   
   
<br />
### Configuring the content of the questionnaire   
// 설문지의 내용 구성   
   
// 설문 1, 2 : 지방자치제도의 역할을 묻는 문항   
// 설문 3, 4, 5 : 응답자의 속성을 묻는 문항   
- Questionnaire 1, 2 : Questions about the role of the local government system   
- Questionnaire 3, 4, 5 : Questions about the attributes of the respondent   
   
#### Encoding Guidelines for Questionnaires   
// 질문지에 대한 부호화 지침   
   
|No|Variable name|English variable name|Input column|Code and Description|
|:---:|:---:|:---:|:---:|:---|
||serial number|ID|1~2||
|1|regional development|C1|4|1, 2, 3, 4, 9 (No response)|
|2|regional economy|C2|6|1, 2, 3, 4, 9 (No response)|
|3|gender|P1|8|1 (Male), 2 (Female), 9 (No response)|
|4|age|P2|10|1, 2, 3, 4, 5, 6, 9 (No response)|
|5|a place of origin|P3|12|1, 2, 3, 4, 5, 6, 7, 9 (No response)|
   
<br />
### Enter as a text file   
// 텍스트 파일로 입력   
   
// ASCII 코드 형식으로 저장된 파일로 아스키 파일이라고 함   
// 한글 2018에서 일정한 양식으로 데이터 입력 후, '파일 - 다른 이름으로 저장 (A)'을 선택하고, 파일 형식을 '텍스트 파일'로 저장   
// 자유형식과 고정형식으로 구분   
// - 자유형식 : 변수와 변수 구분은 공란 (blank) 으로 구분   
// - 고정형식 : 각 변수가 위치할 열 (칼럼) 을 정한 후 입력   
- Files stored in ASCII code format called ASCII files   
- After entering data in a certain format in Hangeul 2018, select 'File - Save as another name (A)' and save the file format as 'Text File'   
- Divide free format and fixed format   
  - free format : Variables and Variables Separated by Blank   
  - fixed format : Specify the column in which each variable will be located and enter it   
   
<br />
### Enter as a spreadsheet or database file   
// 스프레드시트나 데이터베이스 파일로 입력   
   
// 엑셀 등에서 간편한 데이터 입력이 가능함   
// 열은 변수를 나타내고, 행은 케이스를 나타냄   
- Easy data input from Excel, etc.   
- Columns represent variables, rows represent cases   
   
<br />
### Enter data in SPSS   
// SPSS에서 데이터 입력   
   
// 직접 데이터를 입력하거나 텍스트 파일, 엑셀 파일 등을 읽을 수 있음   
- Enter data directly into SPSS. Read text files, Excel files, etc.   
   
<br />
### Enter data in SAS   
// SAS에서 데이터 입력   
   
// SAS 편집기에 데이터를 직접 입력하거나 외부 입력 파일을 읽어 옴   
- Enter data directly into SAS editor or read external input files   
   
<br />
### Enter data in S-Link   
// S-Link에서 데이터 입력   
   
// 직접 S-Link 워크시트에 데이터를 입력하거나 외부의 텍스트 파일이나 엑셀 파일을 읽을 수 있음   
- Enter data directly into the S-Link worksheet, or read external text or Excel files   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
