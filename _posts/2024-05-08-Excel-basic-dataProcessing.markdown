---
layout: post
title:  "Excel: Excel Basic & Data Processing using Excel"
date:   2024-05-08 09:00:00 +0900
categories: [Excel]
---

<style>
    .characterOverline {
        text-decoration : overline;
    }
</style>
   
### Key Features of Excel   
// 엑셀의 주요 기능   
   
// 사용자가 수식을 정의하여 사용할 수 있음   
// 엑셀 함수를 활용한 분석 가능   
// 다양한 통계분석 도구는 데이터의 분석을 쉽게 활용할 수 있게 해줌   
// 연립방정식 풀이 및 최적화 문제 해결 기능 등의 활용으로 실제 업무상의 여러 문제들을 효과적으로 해결   
// 피벗 테이블 기능을 활용하여 데이터를 손쉽게 정리, 요약 가능   
// 데이터 분석 결과와 함께 알맞은 그래프를 제시하는 것이 효과적임   
- Users can define and use expressions   
- Users can analyze using Excel function   
- A variety of statistical tools make it easier to analyze data   
- It can effectively solve various practical problems by using systematic equations and optimization problem solving functions   
- Easily organize and summarize data by leveraging pivot table capabilities   
- It is effective to present the correct graph with the results of the data analysis   
   
<br />
### Basic Terms of Excel   
// 엑셀의 기본 용어   
   
// 통합문서 (workbook)   
// - 데이터 입력이나 분석 작업을 하여 그 결과를 저장하는 하나의 파일   
// - 여러 개의 워크시트로 구성 (Sheet1, Sheet2, Sheet3 등 또는 명칭 부여 가능)   
// 워크시트 (worksheet)   
// - 행과 열의 구조를 갖는 많은 셀로 구성된 작업공간으로 통합문서의 일부임   
// - 통합문서가 한 권의 책, 워크시트는 한 페이지에 해당   
// - 데이터를 입력하고 계산 결과가 표시되며, 열은 ABC.. 로, 행은 123... 으로 표시   
// - 열은 A, B, ..., AA, BB, ..., XFD 까지 16,384개임   
// - 행은 1부터 1,048,576 까지 가능   
// 워크시트 탭 (worksheet tab)   
// - 워크시트의 아래 부분에 위치하며, 각 워크시트의 이름을 지정할 수 있음   
// 셀 (cell)   
// - 열과 행이 만나는 칸   
// 활성 셀   
// - 현재 선택된 셀로 두꺼운 테두리로 표시됨   
// 셀 참조   
// - 각 셀은 열과 행의 조합으로 주소를 가짐 (예시 : C열 5행 셀은 주소가 C5 임)   
// 수식 입력 줄   
// - 활성 셀 (선택된 셀) 의 정보를 보여주고, 데이터를 입력하거나 수정할 수 있으며, 함수식을 입력할 수 있음   
// 상태표시줄   
// - 엑셀 초기화면의 가장 아래 줄로 엑셀의 현재 상태를 표시함   
- Workbook   
  - A single file that performs data input or analysis and stores its results   
  - Organize with multiple worksheets (Sheet1, Sheet2, Sheet3, etc. or Nameable)   
- Worksheet   
  - Workspaces consisting of many cells with row and column structures that are part of the integrated document   
  - Integrated document corresponds to one book, worksheet corresponds to one page   
  - Enter the data and display the calculation results, displaying the column ABC... and the row as 123...   
  - There are 16,384 columns including A, B, ..., AA, BB, ... and XFD   
  - Rows can be from 1 to 1,048,576   
- Worksheet tab   
  - Located at the bottom of the worksheet, each worksheet can be named   
- Cell   
  - A space where columns and rows meet   
- Active Cell   
  - Currently selected cells are marked with a thick border   
- Refer to Cell   
  - Each cell has an address as a combination of columns and rows (Example : Cells in column C and row 5 have a C5 address)   
- Formula Input Line   
  - Displays information about the active cell (selected cell), can enter or modify data, and can enter functional expressions   
- Status bar   
  - Displays the current status of Excel in the bottom line of the Excel initial screen   
   
<br />
### Input of data   
// 데이터의 입력   
   
#### Data-Related Basic Terms   
// 데이터 관련 기본 용어   
   
// 변수   
// - 조사단위로부터 측정되는 속성   
// 케이스   
// - 조사단위에 대한 정보의 집합체   
// 변수명   
// - 변수의 이름   
- Variable   
  - Properties measured in units of investigation   
- Case   
  - A collection of information about a unit of investigation   
- Variable name   
  - Name of the variable   
   
#### Importing a text file that has already been created   
// 이미 만들어진 텍스트 파일 불러오기   
   
// 1. `[파일] - [열기]` 선택하여 불러올 텍스트 파일이 위치한 곳과 파일 이름을 지정   
// 2. 텍스트 마법사 대화상자에서 전체 3단계의 절차를 밟으면 작성된 텍스트 파일을 워크시트에 불러올 수 있음   
// - 텍스트 마법사 1단계 : 원본 데이터의 파일 유형을 '구분 기호로 분리됨' 선택하면 특정 기호로 분리된 형태를 유지하여 불러올 수 있음   
1. Select `[File] - [Open]` to specify the location and the file name of the text file to import   
2. After following the full three steps of the text wizard dialog box, the created text file is imported into the worksheet   
    - Text Wizard Step 1: Select 'separated by delimiter' to keep the file type of the original data separated by a specific symbol and import it   
   
<br />
### Move and copy data   
// 데이터의 이동과 복사   
   
// 이웃하지 않은 복수의 셀은 Ctrl 키를 누른 상태에서 마우스로 원하는 만큼 선택할 수 있음   
- Multiple non-neighboring cells can be selected as many times as you want with your mouse while pressing Ctrl   
   
<br />
### How to use a function   
// 함수 사용법   
   
#### Operator of Excel   
// 엑셀의 연산자   
   
// 엑셀에서는 함수를 사용하여 워크시트데이터를 분석하고, 워크시트 값에 대하여 산술 연산, 비교 연산, 문자 연산, 참조 연산 등을 수행   
- Excel analyzes worksheet data using functions and performs arithmetic, comparison, character, and reference operations on worksheet values   
   
// 연산자의 종류   
// - 산술 연산자, 비교 연산자, 문자 연산자, 참조 연산자 등   
- Type of operator   
  - Arithmetic operator, comparison operator, character operator, reference operator, etc.   
   
#### Arithmetic operator   
// 산술 연산자   
   
// `+` (더하기), `-` (빼기), `/` (나누기), `*` (곱셈), `^` (지수)   
- `+` (plus), `-` (subtraction), `/` (sharing), `*` (multiplication), `^` (exponential)   
   
- Example   
   
```excel
=2^A1
```
   
- Result   
   
```
// A1 이 3 이라면 → 2³
If A1 is 3 → 2³
```
   
- Example   
   
```excel
=SQRT(A1)
```
   
- Result   
   
```
// A1 이 2 라면 → √2 → 1.4142135623731
If A1 is 2 → √2 → 1.4142135623731
```
   
#### Comparison operator   
// 비교 연산자   
   
// `=` (같다), `＞` (크다), `＜` (작다), `＞=` (크거나 같다), `＜=` (작거나 같다), `＜＞` (같지 않다)   
- `=` (equal), `＞` (large), `＜` (small), `＞=` (large or equal), `＜=` (small or equal), `＜＞` (not equal)   
   
#### Character operator (Connecting characters, Combining characters)   
// 문자 연산자 (문자 연결, 문자 합하기)   
   
// `&` (두 값을 연결하여 하나의 문자값 산출)   
- `&` (Connect two values to calculate one character value)   
   
- Example   
   
```excel
=A1&A2
```
   
- Result   
   
```
// A1 이 "컴퓨터", A2가 "과학" 이라면 → "컴퓨터과학"
If A1 is "Computer", A2 is "Science", then → "ComputerScience"
```
   
#### Reference operator   
// 참조 연산자   
   
// `:` (범위)   
// - 예시 : `=SUM(A1:A10)`   
// `,` (합집합)   
// - 예시 : `=SUM(A1:A3, B1:B5)` : 전체 값을 합함   
// `공백` (교집합)   
// - 예시 : `=SUM(A1:A6 A5:A10)` : 중복되는 값들만 합함   
- `:` (scope)   
  - Example : `=SUM(A1:A10)`   
- `,` (union)   
  - Example : `=SUM(A1:A3, B1:B5)` : Sum all values   
- `space` (intersection)   
  - Example : `=SUM(A1:A6 A5:A10)` : Sum of duplicate values only   
   
#### Formality of a common function   
// 일반적인 함수의 형식   
   
// 함수식은 등호 ('=')로 시작   
// `=함수이름(인수, 인수, ..., 인수)` 형식   
// - 예시 : `=AVERAGE(A1:B3)`   
- The functional expression begins with an equal sign ('=')   
- `= FunctionName(argument, argument,..., argument)` format   
  - Example : `=AVERAGE(A1:B3)`   
   
#### How to refer to the cell   
// 셀 참조 방법   
   
// 상대참조   
// - 행 이름이나 열 이름만을 사용하여 셀 참조   
// - 예시 : `A1, D3, = AVERAGE(A2:G2)`   
// 절대참조   
// - 참조하는 셀이나 셀 범위를 표시할 때 "$" 표시 사용   
// - 예시 : `$A$1, $D$3, = AVERAGE($A$2:$G$2)`   
// 혼합참조   
// - 행 이름이나 열 이름의 한쪽에만 "$" 표시하여 참조   
// - 예시 : `$A1, D$3, = AVERAGE($A2:$G2)`   
- Relative reference   
  - Refer to Cells using only row or column names   
  - Example : `A1, D3, = AVERAGE(A2:G2)`   
- Absolute reference   
  - Use a "$" mark to display a reference cell or cell range   
  - Example : `$A$1, $D$3, = AVERAGE($A$2:$G$2)`   
- Mixed reference   
  - Refer by marking "$" only on one side of a row or column name   
  - Example : `$A1, D$3, = AVERAGE($A2:$G2)`   
   
<br />
### Examples of using IF functions   
// IF 함수 사용 예시   
   
// 통계학 점수가 60점 이상이면 '합격', 60점 미만이면 '불합격'으로 표시하시오   
// - IF문은 주어진 조건을 평가하여 참인 경우와 거짓인 경우에 다른 값을 표시함   
- A statistic score of 60 or higher indicates 'pass', and a statistic score of 60 less indicates 'fail'   
  - The IF statement evaluates the given conditions to display different values for true and false   
   
// 형식   
- Format   
   
```excel
// =IF(주어진 조건, 참 값, 거짓 값)
=IF(given conditions, value if true, value if false)
```
   
// 주어진 조건 : 참 또는 거짓으로 판정되는 값이나 식   
// 참 값 : 주어진 조건이 참일 때 얻게 되는 결과값   
// 거짓 값 : 주어진 조건이 거짓일 때 얻게 되는 결과값   
- given conditions : A value or expression that is judged to be true or false   
- value if true : The result value obtained when a given condition is true   
- value if false : The result value obtained when a given condition is false   
   
```excel
// =IF(A1>=60, "합격", "불합격")
=IF(A1>=60, "pass", "fail")
```
   
```excel
// =IF(AND(A1>=60, A2>=60), "합격", IF(OR(A1<60, A2<60), "과락"))
=IF(AND(A1>=60, A2>=60), "pass", IF(OR(A1<60, A2<60), "failure"))
```
   
<br />
### Using the Function Wizard   
// 함수 마법사 이용   
   
// 1. 계산된 함수 값이 입력될 셀 선택   
// 2. 함수 마법사를 클릭하여 대화 상자 이용   
// 3. 함수의 인수로 사용될 셀의 범위를 직접 마우스로 드래그하여 설정   
// 4. 올바르게 인수가 지정되었는가를 검토하여 확인 선택   
1. Select the cell to which the calculated function value is entered   
2. Use dialogs by clicking on the Function Wizard   
3. Set the range of cells to be used as arguments for the function by dragging directly with the mouse   
4. Review to select if the argument is correctly specified   
   
<br />
### Frequently used Excel functions   
// 자주 사용하는 엑셀 함수들   
   
// AVERAGE 함수   
// - 인수의 산술 평균을 구함   
// - 예시 : `=AVERAGE(number1, number2, number3, ...)`   
- AVERAGE function   
  - Calculated the arithmetic mean of the arguments   
  - Example : `=AVERAGE(number1, number2, number3, ...)`   
   
// VAR 함수   
// - 표준자료의 표본분산을 구함   
// -- 표본분산 (variance) s² = <sup>∑(x<sub>i</sub> - <span class="characterOverline">X</span>)²</sup> / <sub>n - 1</sub>   
// - 예시 : `=VAR(number1, number2, number3, ...)`   
- VAR function   
  - Find the sample variance of the standard data   
    - variance s² = <sup>∑(x<sub>i</sub> - <span class="characterOverline">X</span>)²</sup> / <sub>n - 1</sub>   
  - Example : `=VAR(number1, number2, number3, ...)`   
   
// STDEV 함수   
// - 표본자료의 표준편차를 구함   
// -- 표본표준편차 (standard deviation) s = √s²   
// - 예시 : `=STDEV(number1, number2, number3, ...)`   
- STDEV function   
  - Find the standard deviation of the sample data   
    - standard deviation s = √s²   
  - Example : `=STDEV(number1, number2, number3, ...)`   
   
// MEDIAN 함수   
// - 인수의 중앙값을 구함   
// - 예시 : `=MEDIAN(number1, number2, number3, ...)`   
- MEDIAN function   
  - Obtain the median value of the argument   
  - Example : `=MEDIAN(number1, number2, number3, ...)`   
   
// MAX 함수   
// - 데이터의 최대값을 구함   
// - 예시 : `=MAX(number1, number2, number3, ...)`   
- MAX function   
  - Obtain maximum value of the data   
  - Example : `=MAX(number1, number2, number3, ...)`   
   
// MIN 함수   
// - 데이터의 최소값을 구함   
// - 예시 : `=MIN(number1, number2, number3, ...)`   
- MIN function   
  - Obtain minimum value of the data   
  - Example : `=MIN(number1, number2, number3, ...)`   
   
<br />
### Processing data using Excel   
// 엑셀을 사용한 데이터 처리   
   
#### Statistical Analysis of Data   
// 데이터에 대한 통계 분석   
   
// 기술통계량 (descriptive statistics)   
// - 데이터의 전반적인 분포 형태와 특성을 쉽게 파악하기 위한 목적으로 데이터를 정리, 요약한 수치   
// - `[데이터] 탭 - [분석] 그룹 - [데이터 분석] - [기술 통계법]` 이용   
- Descriptive statistics   
  - Figures organized and summarized data for the purpose of easily identifying the overall distribution and characteristics of the data   
  - Using the `[Data] tab - [Analysis] group - [Data Analysis] - [Descriptive Statistics]`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelAnalyticalTool6.png)
   
#### In Excel, how to add 'Data Analysis' if it doesn't appear   
// 엑셀에서 '데이터 분석'이 나타나지 않는 경우 추가하는 방법   
   
// `[파일] - [옵션] - [추가 기능] - [분석 도구]` 선택   
- Select `[File] - [Options] - [Additional Features] - [Analytic Tools]`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelAnalyticalTool1.png)
   
// `[추가 기능] - [분석 도구 팩]` 선택   
- Select `[Additional] - [Analytic Tool Pack]`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelAnalyticalTool2.png)
   
// `[개발 도구] - [분석도구 팩]` 체크   
- Check `[Development Tool] - [Analytic Tool Pack]`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelAnalyticalTool3.png)
   
// `[데이터] 탭 - [분석] 그룹 - [데이터 분석]` 선택하여 사용   
- Select and use the `[Data] tab - [Analysis] group - [Data Analysis]`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelAnalyticalTool4.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelAnalyticalTool5.png)
   
#### Data Analysis Tools from Excel   
// 엑셀에서 제공하는 데이터 분석 도구   
   
// 거의 모든 기초적인 통계분석 가능   
// - 분산분석   
// - 상관분석   
// - 기술통계분석   
// - 이동평균법   
// - 지수 평활법   
// - 히스토그램   
// - 난수생성   
// - 순위와 백분율   
// - 회귀분석   
// - t-검정   
// - 표본 추출   
- Almost all basic statistics are available   
  - ANOVA (analysis of variance)   
  - Correlation analysis   
  - Descriptive statistics   
  - Moving averages   
  - Exponential smoothing method   
  - Histogram   
  - Random number generation   
  - Rank and percentage   
  - Regression   
  - t-test   
  - Sampling   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
