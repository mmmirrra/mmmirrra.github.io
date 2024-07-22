---
layout: post
title:  "Excel: Function"
date:   2024-05-10 09:00:00 +0900
categories: [Excel]
---

### Rules of Use of Functions   
// 함수 사용의 규칙   
   
// 수식은 등호 (=) 로 시작   
// 함수 이름 다음에 인수로 묶는 양쪽 괄호는 반드시 필요   
// 인수는 숫자, 셀 범위, 논리값, 문자값, 다른 함수도 가능   
// 인수가 여러 개 사용되는 경우 콤마 (,) 로 분리   
- Expression statement begins with equal sign (=)   
- A function name followed by an argument must be enclosed in double parentheses   
- Arguments can include numbers, cell ranges, logical values, character values, and other functions   
- Separate with comma(,) when multiple arguments are used   
   
<br />
### Example of using Excel fill and function   
// 엑셀 채우기와 함수 사용 예시   
   
// 오늘 1원 저금하고 내일은 그 2배, 그 다음은 전날은 전날의 2배, 이렇게 저금하면 며칠째 되는 날에 누적액이 1억원을 돌파하는지 찾는 함수를 작성하시오   
- Write a function to find out how many days the accumulated amount exceeds 100 million won if you save 1 won today, 2 times that tomorrow, and 2 times that the previous day.   
   
// 1. A1 셀에 '날짜', B1 셀에 '저금액', C1셀에 '누적 저금액' 입력   
// 2. A2 셀과 A3 셀에 각각 1과 2를 입력하고, 자동 채우기 기능을 이용해서 '드래그 & 드롭'하여 30까지 채우기 실행   
// 3. B2 셀에 첫 날의 저금액인 '1'을 입력하고, C2 셀에 '=B2'를 입력, B3 셀에 '=2* B2'를 입력, C3 셀에 '=C2 + B3'를 입력   
// 4. B3:C3 의 셀 범위를 선택하고 채우기 핸들을 '드래그 & 드롭' 해서 30일째 되는 날까지 채우기 실행   
// 5. 누적액이 처음으로 1억원을 넘는 날짜는 27일째임을 확인   
1 . Enter 'Date' in A1 cell, 'Savings' in B1 cell, and 'Cumulative Savings' in C1 cell   
2 . Enter 1 and 2 in A2 and A3 cells respectively and 'drag & drop' using the auto-filling function to fill up to 30   
3 . Enter '1' which is the storage amount of the first day in the B2 cell, '=B2' in the C2 cell, '=2*B2' in the B3 cell, and '=C2 + B3' in the C3 cell   
4 . Select the cell range for B3:C3 and 'drag & drop' the fill handle to fill by day 30th   
5 . Confirmation that the date of accumulation exceeding KRW 100 million for the first time is the 27th day   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelDragFill1.png)
   
<br />
### Example of using SUM function to an average GPA   
// SUM 함수를 이용하여 평점 평균 구하는 예시   
   
// 교과목의 성적 등급 및 평점   
- Grades and GPA of the grade   
   
|Grade|A+|A0|A-|B+|B0|B-|C+|C-|C-|D+|D0|D-|F|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|GPA|4.3|4.0|3.7|3.3|3.0|2.7|2.3|2.0|1.7|1.3|1.0|0.7|0|
   
// 어느 학생의 성적표에 대한 평점 평균 구하기   
- Obtaining the average GPA of a student's grade on his or her report card   
   
|과목명<br />Course|신청 학점<br />Applied credit|성적<br />Grade|
|:---|:---:|:---:|
|경영학개론<br />Introduction to Business Administration|3|B0|
|세계의 역사<br />The history of the world|3|A-|
|컴퓨터의 이해<br />Understanding of computers|3|A0|
|데이터정보처리 입문<br />Introduction to Data Information Processing|3|A+|
|인터넷서비스<br />Internet service|3|B+|
|계<br />Sum|15||
   
// - 1. 해당 과목의 성적에 대응하는 평점을 각각 입력   
// - 2. E1 셀에 '학점 * 평점' 입력, E2 셀에 함수 '=B2 * D2' 입력   
// - 3. E2 셀을 선택하고 '드래그 & 드롭'으로 E6 셀까지 채움. 이 과정을 통해서 각 과목에 대한 '학점 x 평점' 계산   
// - 4. E7 셀에 '=SUM(E2:E6)/B7' 입력하여 평점평균 계산   
// -- 평점평균 = <sup>(학점 x 평점)의 합계</sup> / <sub>학점의 합계</sub> = <sup>∑학점 x 평점</sup> / <sub>∑학점</sub>   
- 1 . Enter each GPA corresponding to the grade of the subject   
- 2 . Enter 'Credit * GPA' in E1 cell, and function '=B2 * D2' in E2 cell   
- 3 . Select the E2 cell and fill it up to the E6 cell with 'drag & drop'. Calculate 'Credit x GPA' for each subject through this course   
- 4 . Enter '=SUM(E2:E6)/B7' in E7 cell to calculate the average GPA   
    - an average GPA = <sup>the sum of (credit x GPA)</sup> / <sub>the sum of one's credits</sub> = <sup>∑credit x GPA</sup> / <sub>∑credit</sub>   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelSum1.png)
   
// SUMPRODUCT 함수   
// - 배열의 대응되는 값끼리 곱해서 합을 구해주는 기능   
- SUMPRODUCT Function   
  - A function that multiplies the corresponding values of an array to obtain a sum   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelSumproduct1.png)
   
<br />
### Example of using a date/time function   
// 날짜/시간 함수 사용 예시   
   
// `=DATE(year, month, day)`   
// - 특정 날짜의 일련 번호를 구해주는 함수   
`=DATE(year, month, day)`   
  - A function to obtain a serial number for a particular date   
   
// `=YEAR(날짜 또는 숫자)`   
// - 날짜에 해당하는 연도를 표시해주는 함수   
`=YEAR(date or number)`   
- Function to display the year corresponding to the date   
   
// `=NOW()`   
// - 현재 시점을 나타내는 기능으로 인수가 필요없는 함수   
// - 입력하는 시점마다 값이 변화함   
`=NOW()`   
  - Function that represents the current point in time and does not require arguments   
  - The value changes every time you enter it   
   
<br />
### Function that does not require arguments   
// 인수가 필요 없는 함수   
   
// `=RAND()`   
// - 랜덤 숫자 구하는 함수   
`=RAND()`   
  - Random numeric function   
   
// `=PI()`   
// - 파이 값을 구하는 함수   
`=PI()`   
  - function to find the value of the pi   
   
<br />
### Example of a text function   
// 텍스트 함수 예시   
   
// `=LEFT(text, num_chars)`   
// - 문자열의 첫 문자부터 지정된 개수의 문자를 표시   
// -- 예시   
// --- A1 셀에 "대한민국" 이 입력되었다면   
// --- `=LEFT(A1, 2)` → `"대한"`   
`=LEFT(text, num_chars)`   
  - Display the specified number of characters from the first character of the string   
    - Example   
      - If "Republic of Korea" is entered in the A1 cell   
      - `=LEFT(A1, 2)` → `"Re"`   
   
// `=RIGHT(text, num_chars)`   
// - 문자열의 마지막 문자부터 지정된 개수의 문자를 표시   
// -- 예시   
// --- `=RIGHT("Sale Price", 5)` → `"Price"`   
`=RIGHT(text, num_chars)`   
  - Display the specified number of characters from the last character of the string   
    - Example   
      - `=RIGHT("Sale Price", 5)` → `"Price"`   
   
// `=MID(text, start_num, num_chars)`   
// - 문자열의 지정한 위치로부터 지정한 개수의 문자를 표시   
// -- 예시   
// --- `=MID("대한민국", 3, 2)` → `"민국"`   
`=MID(text, start_num, num_chars)`   
  - Displays the specified number of characters from the specified location of the string   
    - Example   
      - `=MID("Republic of Korea", 3, 2)` → `"pu"`   
   
- Example   
   
// A1 에 `790815` 가 입력되어 있다면   
// 생년월일은 B1 에 `=DATE(LEFT(A1,2), MID(A1,3,2), MID(A1,5,2))` 입력 → `1975-08-15`   
// 나이는 C1에 `=YEAR(NOW())-YEAR(B1)` 입력 → `45`   
- If '790815' is entered in A1   
- For the date of birth, enter `=DATE(LEFT(A1,2), MID(A1,3,2), MID(A1,5,2))` in B1 → `1975-08-15`   
- For age, enter `=YEAR(NOW())-YEAR(B1)` in C1 → `45`   
   
<br />
### Example of calculation of total principal and interest   
// 원리합계 계산 예시   
   
// 복리로 계산되는 경우에 현재의 금액 p에 대한 일정 기간 후의 원리합계 G 는 연이율을 r, 기간을 n으로 주어졌을 때 다음과 같이 계산됨   
// - G = p x (1 + r)ⁿ   
- When compounded, the sum G of principle after a certain period of time for the current amount p is calculated as follows given the annual rate as r and the period as n   
  - G = p x (1 + r)ⁿ   
   
// 원금이 1,000만원인 경우 연 4.5%, 5.0%, 5.5%, 6.0% 로 주어진 경우에 향후 20년이 경과하였을 때 원리합계가 얼마나 차이가 생기는지 계산하시오   
- If the principal amount is KRW 10 million, calculate the difference in the sum of principal and interest over the next 20 years if interest is given at 4.5%, 5.0, 5.5%, or 6.0 percent per annum   
   
// - 1. B5 셀에 `=$B$1*(1+B$2)^$A5` 을 입력하고, 채우기 기능을 이용하여 E5 까지 채움   
// -- 원금은 절대참조 이용   
// -- 연이율과 경과년수는 혼합참조 이용   
// - 2. B5:E5 까지 선택하고 '드래그 & 드롭'으로 20년이 경과한 후까지 채움   
- 1 . Enter `=$B$1*(1+B$2)^$A5` in the B5 cell and fill up to E5 using the fill function   
    - Use absolute reference for principal   
    - Annual rate and number of years elapsed use mixed reference   
- 2 . Choose B5:E5 and fill it up after 20 years with 'drag & drop'   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelTotalPrincipalAndInterest1.png)
   
// 연이율 1%의 차이가 20년 후에 약 500만원 이상의 차이로 나타남   
- The difference in annual interest rate of 1% appears to be more than KRW 5 million after 20 years   
   
<br />
### Draw a function graph and find a solution   
// 함수 그래프 그리기와 해 찾기   
   
// 함수 기능과 차트 기능을 활용하면 간단한 함수의 그래프 개형 뿐만 아니라 방정식의 해도 구할 수 있음   
- Functional and chart functions allow you to obtain a graph overview of a simple function, as well as a diagram of the equation   
   
#### Function graph, and example of approximate solution finding   
// 함수 그래프 그리고, 근사적인 해 찾기 예시   
   
// 함수의 그래프 개형을 구간 (-3, 3) 에서 그려보고, 그 구간에서 'fx() = 0' 을 만족하는 근사적인 해를 찾으시오   
// - `f(x) = -x³ + 2x² - 2x + 3`   
// -- 1. -3.0 부터 3.0 까지 0.1 간격으로 채우기 기능 실행   
// -- 2. B2 셀에는 `=-A2^3+2*A2^2-2*A2+3` 입력   
// -- 3. 나머지 셀들에 대해서 '드래그 & 드롭'으로 채워 넣음   
// -- 4. (-3, 3) 범위에서 함수의 그래프 그리기   
// --- `[삽입] 탭 - [차트] 그룹 - [분산형(X, Y) 또는 거품형 차트 삽입] - [곡선이 있는 분산형]` 선택   
// ∴ 근사적인 해 = 1.80   
- Draw a graph of the function in interval (-3, 3) and find an approximate solution that satisfies 'fx() = 0' in that interval   
  - `f(x) = -x³ + 2x² - 2x + 3`   
    - 1 . Perform fill function from -3.0 to 3.0 at 0.1 intervals   
    - 2 . Enter `=-A2^3+2*A2^2-2*A2+3` in B2 cells   
    - 3 . Fill the remaining cells by 'drag & drop'   
    - 4 . Draw a graph of a function in the range (-3, 3)   
      - Select `[Insert] Tab - [Chart] Group - [Insert Distributed (X, Y) or Bubble Chart] - [Distributed with Curves]`   
∴ an approximate solution = 1.80   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelFunctionGraph1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelFunctionGraph2.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelFunctionGraph3.png)
   
#### Example of using an approximate solution to find a target value   
// 근사적인 해를 이용하여 목표값 찾기 예시   
   
// 함수 `f(x) = -x³ + 2x² - 2x + 3` 을 만족하는 정확한 해는 엑셀 목표값 찾기 기능을 이용하면 편리하게 구할 수 있음   
// 함수 그래프 그리기를 통해 얻은 근사적인 해는 1.80 근처의 값임을 알 수 있음   
- The exact solution that satisfies the function `f(x) = -x³ + 2x² - 2x + 3` can be conveniently obtained using the Excel target value search function   
- You can see that the approximate solution obtained by drawing a function graph is a value near 1.80   
   
// 목표값 찾기 기능 이용   
// - 1. 워크시트에 구하고자 하는 함수식에 대한 근사적인 해 입력   
// -- 이 문제에서는 편의상 A2 셀에 1.80 입력   
// - 2. B2 셀에 `=-A2^3+2*A2^2-2*A2+3` 입력   
// - 3. `[데이터] 탭 - [예측] 그룹 - [가상분석] - [목표값 찾기]` 선택   
// ∴ 목표값 = 1.8105   
- Use the Find Target feature   
  - 1 . Enter an approximate solution to the function expression you want to obtain in the worksheet   
    - For convenience, enter 1.80 in A2 cell   
  - 2 . Enter `=-A2^3+2*A2^2-2*A2+3` in B2 cells   
  - 3 . Select `[Data] Tab - [Prediction] Group - [Virtual Analysis] - [Find Target]'   
∴ Target = 1.8105   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelFindTarget1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelFindTarget2.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelFindTarget3.png)
   
<br />
### Example 1 Calculating Approximate Integral Values   
// 근사 적분값 계산 예시 1   
   
- ∫<sup>5</sup><sub>1</sub>x²dx = [<sup>1</sup> / <sub>3</sub>x³]<sup>5</sup><sub>1</sub> = <sup>125</sup> / <sub>3</sub> - <sup>1</sup> / <sub>3</sub> = <sup>124</sup> / <sub>3</sub> = 41.3333   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegralformula1.png)
   
// 단계 1. 먼저 구간 [a, b] 를 n 개로 등분함   
// - 각 부분의 밑변의 길이는 <sup>b - a</sup> / <sub>n</sub> 으로 동일   
// 단계 2. 분할된 n 개의 직사각형 넓이를 왼쪽부터 S₁, S₂, ..., S<sub>n</sub> 로 표시   
// - S<sub>k</sub> = <sup>f(x<sub>k - 1</sub>) + f(x<sub>k</sub>) </sup> / <sub>2</sub> x Δx   
// -- 직사각형 넓이 = 밑변 길이 x 높이   
// -- 여기서   
// --- Δx = <sup>b - a</sup> / <sub>n</sub>   
// --- x<sub>k</sub> = a + kΔx   
// 단계 3. S₁, S₂, ..., S<sub>n</sub> 을 모두 합하면 면적의 근사값이 됨   
// - n 을 늘림에 따라 I = ∑<sup>n</sup><sub>k - 1</sub>S<sub>k</sub> 는 더 정확한 근사값이 됨   
// ∴ 근사 적분값 = 41.44   
- Step 1. First, divide the interval [a, b] into n equal parts   
  - The length of the base of each part is the same as <sup>b - a</sup> / <sub>n</sub>   
- Step 2. Display the divided n rectangular areas as S₁, S₂, ..., S<sub>n</sub> from the left   
  - S<sub>k</sub> = <sup>f(x<sub>k - 1</sub>) + f(x<sub>k</sub>) </sup> / <sub>2</sub> x Δx   
    - Rectangular Width = Bottom Length x Height   
    - Here   
      - Δx = <sup>b - a</sup> / <sub>n</sub>   
      - x<sub>k</sub> = a + kΔx   
- Step 3. The sum of S₁, S₂, ..., S<sub>n</sub> becomes an approximation of the area   
  - I = ∑<sup>n</sup><sub>k - 1</sub>S<sub>k</sub> becomes a more accurate approximation as n is increased   
∴ Approximate integral value = 41.44   
   
// 밑변의 길이 계산   
- Calculation of the length of the base   
  - <sup>b - a</sup> / <sub>n</sub>   
  - Δx = <sup>b - a</sup> / <sub>n</sub>   
  - x<sub>k</sub> = a + kΔx   
   
// f(x), 높이, 직사각형 넓이 계산   
- f(x), height, rectangular area calculation   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral1-1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral1-2.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral1-3.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral1-4.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral1-5.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral1-6.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral1-7.png)
   
<br />
### Example 2 Calculating Approximate Integral Values   
// 근사 적분값 계산 예시 2   
   
- I = ∫<sup>2</sup><sub>1</sub><sup>1</sup> / <sub>√2π</sub>e<sup>-<sup>x²</sup> / <sub>2</sub></sup>dx = 0.1359   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegralformula2.png)
   
// ∴ 근사 적분값 = 0.136   
∴ Approximate integral value = 0.136   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral2-1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral2-2.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral2-3.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral2-4.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral2-5.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral2-6.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral2-7.png)
   
// 정규분포 함수로 구한 참값과 비교해보면 거의 비슷한 값임을 알 수 있음   
- When compared to the true value obtained by the normal distribution function, it is almost similar   
- `=NORM.DIST(2,0,1,1)-NORM.DIST(1,0,1,1)`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelIntegral2-8.png)
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
