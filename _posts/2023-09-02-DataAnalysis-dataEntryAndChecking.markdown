---
layout: post
title:  "Introduction to Data Analysis: Data entry and checking"
date:   2023-09-02 09:00:00 +0900
categories: [Data Analysis]
---

## Concept of data   
   
<br />
### Data   
   
- Organized information collected about a topic of interest.   
- Data in a general sense refers to organized information about a subject regardless of the form of expression such as numbers, letters, or pictures.   
   
<br />
### Characteristics of the data   
   
- What is gained about a topic of interest   
- Collected and organized in certain rules and forms suitable for analysis   
- Converted into useful information through the analysis process   
- Collected through survey or experiment and converted into appropriate form   
   
<br />
### Statistical data   
   
- Data suitable for numerical calculations and statistical analysis.   
   
<br />
### Purpose of data analysis   
   
- Accurate identification of natural and social phenomena (characteristics of groups).   
- Identify why such a phenomenon occurred (causal relationship).   
- Discovering hidden laws in economic and social phenomena.   
-→ Helps make rational decisions by predicting future situations.   
   
   
## Levels of measurement and types of data   
   
<br />
### How to collect data   
   
- Obtained by measuring using a designated measurement method (measurement tool, questionnaire) from a survey unit or experimental unit through statistical surveys, experiments, observations, etc.   
- Measurement: The task of observing certain characteristics of each survey unit according to certain standards and assigning a numerical value to each survey unit.   
- Example: When the weight, intelligence, or employment status of the sampled people are observed and expressed as figures   
- → The entire measured data is called data.   
   
<br />
### Basic terminology related to data   
   
- case, record: A collection of information about a unit of survey in a data set   
- variable, field: Individual properties measured from each survey unit   
  - Example: Sample 10 people from an organization and when investigating name, gender, age, education level, and monthly salary (unit: 10,000 won).   
    - Case 1: [Name: Hong], [Gender: Male], [Age: 30], [Education: High school graduate] [Monthly salary: 2 million won]   
    - Case 2: [Name: Park], [Gender: Female], [Age: 31], [Education: College graduate], [Monthly salary: 2.3 million won]   
    - Case 3: [Name: Lim], [Gender: Male], [Age: 27], [Education: .], [Monthly salary: 2.1 million won]   
   
Matrix form representation of dat   
   
|Name|Gender|Age|Education|Monthly salary|
|:---:|:---:|:---:|:---:|:---:|
|Hong|Male|30|High school graduate|2 million won|
|Park|Female|31|College graduate|2.3 million won|
|Lim|Male|27|.|2.1 million won|
   
- Displaying data in matrix form makes it easier to understand.   
- Each row becomes a case (record), and each column becomes a variable (field).   
- In Lim's case, the "." in education level indicates a missing value.   
   
<br />
### Level of measurement   
   
- Depending on the measurement level, there are divided into nominal scale, ordinal scale,  interval scale, and ratio scale.   
- Depending on the scale of measurement, the 'level of information provided' and the 'analytic methods available for data analysis' vary.   
   
<br />
### Nominal scale   
   
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
   
   
## Data Input Process   
   
<br />
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
- Envisioning how to input data obtained from survey/experiment in a simpler and more effective way to analyze it   
   
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
   
   
## Checking the entered data   
   
<br />
### debugging   
// 디버깅   
   
// 입력오류나 또는 조사상 실수로 인한 오류 (bug) 를 찾아 수정할 목적으로 데이터 세트를 검토하고 분석하는 것   
- Reviewing and analyzing data sets for the purpose of finding and correcting errors caused by input errors or investigative errors   
   
<br />
### Check data input errors (if data is large)   
// 데이터 입력 오류 점검 (데이터가 큰 경우)   
   
// 각 변수의 입력 범위를 확인하는 방법   
// 변수들간의 논리적 일관성 여부를 확인하는 방법   
- To check the input range of each variable   
- To check for logical consistency between variables   
   
<br />
### To check the input range of each variable   
// 각 변수의 입력 범위를 확인하는 방법   
   
// 예시   
// - 응답자의 성별을 나타내는 변수에 대해서 남자 (1), 여자 (2)로 나타낸 경우   
// - → 변수 값이 1보다 작거나 2보다 큰 경우가 있다면 입력 과정상의 오류이거나 응답자의 잘못된 응답 또는 조사원의 실수로 발생하였다고 볼 수 있음   
- Example   
  - When a variable representing the gender of the respondent is expressed as male (1) and female (2)   
  - → If the variable value is less than 1 or greater than 2, it can be considered an error in the input process or an incorrect response from the respondent or a mistake from the investigator   
   
<br />
### To check for logical consistency between variables   
// 변수들간의 논리적 일관성 여부를 확인하는 방법   
   
// 예시 : 환자의 성별과 암의 종류간에 교차표 작성   
Example : Create a cross-table between the patient's gender and the type of cancer   
   
|gender|stomach cancer|lung cancer|breast cancer|uterine cancer|others|total|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|male (1)|8|12|0|3|4|27|
|female (2)|5|3|9|7|2|26|
   
// - 남자는 자궁암이 발생할 수 없음에도 불구하고, 3명의 환자가 자궁암으로 입원하였음   
// -- → 해당 케이스의 관측값을 확인하여 환자 성별이나 암 종류에 대한 입력오류 여부 확인   
  - Three patients were hospitalized for uterine cancer, even though the man could not develop uterine cancer   
    - → Check the case's observations for input errors for patient gender or cancer type   
   
<br />
<cite>Source: Department of Computer Science, Korea National Open University</cite>
