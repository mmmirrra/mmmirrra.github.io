---
layout: post
title:  "Introduction to Data Analysis: Data Analysis Using R"
date:   2023-09-12 09:00:00 +0900
categories: [Data Analysis]
---

## Data Analysis Using R   
// R을 활용한 자료분석   
   
<br />
### Introduction to R   
// R 소개   
   
// 통계 소프트웨어 시스템 (statistical software system)   
// - 데이터를 효율적으로 처리하고 분석할 수 있으며, 다양한 통계적 분석과 그래프 등을 구현할 수 있는 통계시스템   
// 대화형 언어 (interpreted language)   
// - 언어가 입력된 즉시 시행이 됨   
// 객체지향 (object-oriented) 시스템   
// - R은 객체를 다룰 수 있도록 구성되어 있음   
// - 데이터, 변수, 행렬 등은 모두 객체이며, 객체는 연산자 `<-` 또는 `=`에 의해 생성됨   
- Statistical Software System   
  - A statistical system that can efficiently process and analyze data and implement various statistical analyses and graphs   
- Interpreted language   
  - Enforcement as soon as language is entered   
- Object-oriented system   
  - R is configured to handle objects   
  - Data, variables, matrices, etc. are all objects, and objects are created by operators `<-` or `=`   
   
<br />
### Function of R   
// R의 기능   
   
// 자료처리 기능   
// - 자료의 구성, 소팅, 결합 등이 프로그램 처리로 쉽게 이루어짐   
// 자료분석 기능   
// - 자료를 분석하기 위해 필요한 통계분석 함수 및 분석 결과 제공 등이 다양함   
// 언어 기능   
// - 함수문을 쉽게 작성할 수 있으며, C언어 및 FORTRAN 언어 등과 인터페이스 (interface) 가 가능   
// 그래픽스 기능   
// - 대화형 그래픽스에 의한 자료분석의 기능 및 분석결과의 그래픽스 처리 기능이 뛰어남   
- Data processing function   
  - Composition, sorting, combining, etc. of data are easily processed by program processing   
- Data analysis function   
  - Statistical functions and analysis results required to analyze data vary   
- Language function   
  - Function statements can be easily written and interfaces with C language and FORTRAN language   
- Graphics function   
  - Interactive graphics for better data analysis and graphics processing of analysis results   
   
<br />
### Download R   
// R 다운로드   
   
- https://cran.yu.ac.kr/   
   
<br />
## Read data   
// 자료 읽기   
   
<br />
### Questionnaire Example   
// 설문지 예시   
   
// 설문   
// - 어느 집단에서 표본을 10명 추출하여 다음과 같은 4개 문항에 대하여 설문조사를 실시하였다   
// -- 문항 1 : 귀하의 성별은?   
// --- (1) 남자 (2) 여자   
// -- 문항 2 : 귀하의 나이는?   
// --- (단위 : 세)   
// -- 문항 3 : 교육정도는?   
// --- (1) 중졸이하 (2) 고졸 (3) 대졸 이상   
// -- 문항 4 : 월수입   
// --- (단위 : 만원)   
- Questionnaire   
  - Ten people were sampled from a group, and a survey was conducted on the following four questions   
    - Question 1 : What is your gender?   
      - (1) Male (2) Female   
    - Question 2 : How old are you?   
      - (Unit : Age)   
    - Question 3 : What is your education level?   
      - (1) A middle school graduate or lower (2) A high school graduate (3) A college graduate or higher   
    - Question 4 : What's your monthly income?   
      - (Unit : 10,000 won)   
   
|Serial number|Variable 1 (sex)|Variable 2 (age)|Variable 3 (edu)|Variable 4 (salary)|
|:---:|:---:|:---:|:---:|:---:|
|1|1|21|2|150|
|2|2|22|1|100|
|3|1|33|2|200|
|4|2|33|3|220|
|5|1|28|2|170|
|6|1|41|3|300|
|7|2|39|2|290|
|8|1|32|3|220|
|9|2|44|1|370|
|10|1|55|3|410|
   
<br />
### Read text data   
// 텍스트 자료 읽기   
   
// 빈칸으로 구분된 텍스트 파일 읽기 : `read.table`   
// csv로 된 텍스트 파일 읽기 : `read.csv`   
- Read a blanked text file : `read.table`   
- Read text files written in csv : `read.csv`   
   
```r
> ex8 = read.table("c:/Users/Desktop/DataAnalysis_ex8-1.csv", header=T)
> # ex8 = read.csv("c:/Users/Desktop/DataAnalysis_ex8-1.csv")
> # 앞에서부터 일부분의 행 표기
> # Mark part of the line from the beginning
> head(ex8)
  id sex age edu salary
1  1   1  21   2    150
2  2   2  22   1    100
3  3   1  33   2    200
4  4   2  33   3    220
5  5   1  28   2    170
6  6   1  41   3    300
> # 앞에서부터 3개의 행 표기
> # Mark 3 lines from the beginning
> head(ex8, 3)
  id sex age edu salary
1  1   1  21   2    150
2  2   2  22   1    100
3  3   1  33   2    200
> # 뒤에서부터 일부분의 행 표기
> # Mark part of a line from the back
> tail(ex8)
   id sex age edu salary
5   5   1  28   2    170
6   6   1  41   3    300
7   7   2  39   2    290
8   8   1  32   3    220
9   9   2  44   1    370
10 10   1  55   3    410
> # 뒤에서부터 3개의 행 표기
> # Mark 3 lines from the back
> tail(ex8, 3)
   id sex age edu salary
8   8   1  32   3    220
9   9   2  44   1    370
10 10   1  55   3    410
```
   
<br />
### Read Excel data   
// 엑셀 자료 읽기   
   
- package : xlsx, readxl   
   
// R에서 `packages > Install packages >` 메뉴에서 `xlsx, readxl` 를 설치 후 사용 가능   
- Available after installing `xlsx, readxl` in the `packages > Install packages >` menu in R   
   
// `xlsx`로 읽기   
- Read using `xlsx`   
   
```r
> # 패키지 설정
> # Package Settings
> library(xlsx)
> ex8_xls = read.xlsx("c:/Users/Desktop/DataAnalysis_ex8-1.xlsx", 1)
> head(ex8_xls, 3)
  id sex age edu salary
1  1   1  21   2    150
2  2   2  22   1    100
3  3   1  33   2    200
```
   
// `readxl`로 읽기   
- Read using `readxl`   
   
```r
> library(readxl)
> ex8_xl = read_excel(path = "c:/Users/Desktop/DataAnalysis_ex8-1.xlsx")
> head(ex8_xl, 3)
# A tibble : 3 × 5
     id   sex   age   edu salary
  <dbl> <dbl> <dbl> <dbl>  <dbl>
1     1     1    21     2    150
2     2     2    22     1    100
3     3     1    33     2    200
```
   
<br />
## Obtaining descriptive statistics   
// 기술통계량 구하기   
   
// 변수 월급여(salary)의 평균 및 표준편차 구하기   
- Find the mean and standard deviation of the variable monthly salary   
   
```r
> ex8 = read.csv("c:/Users/Desktop/DataAnalysis_ex8-1.csv")
> head(ex8, 3)
  id sex age edu salary
1  1   1  21   2    150
2  2   2  22   1    100
3  3   1  33   2    200
> names(ex8)    # Display column name
[1] "id"     "sex"    "age"    "edu"    "salary"
> mean(ex8$salary)    # Average
[1] 243
> sd(ex8$salary)    # Standard deviation
[1] 98.21179
> summary(ex8$salary)    # Five-number summary + mean
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
  100.0   177.5   220.0   243.0   297.5   410.0 
```
   
// attach()를 사용하면 변수명을 바로 사용할 수 있음   
- attach() allows variable names to be used immediately   
   
```r
> # 해당 객체 고정 
> # attach that object
> attach(ex8)
> mean(salary)
[1] 243
> sd(salary)
[1] 98.21179
> summary(salary)    # five-number summary + mean
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
  100.0   177.5   220.0   243.0   297.5   410.0 
```
   
<br />
### Obtaining descriptive statistics by group   
// 그룹별 기술통계량 구하기   
   
// 성별과 교육정도별로 월급여 (salary) 의 평균 및 표준편차 구하기   
- Calculate the average and standard deviation of monthly salary by gender and education level   
   
```r
> tapply(ex8$salary, ex8$sex, mean)
       1        2 
241.6667 245.0000 
> tapply(ex8$salary, ex8$sex, sd)
        1         2 
 97.45084 114.45523 
> mean_Sal_Sex = tapply(ex8$salary, ex8$sex, mean)
> # 행 이름 지정
> # Name a row
> rownames(mean_Sal_Sex) = c("Male","Female")
> mean_Sal_Sex
      Male       Female 
241.6667 245.0000 
```
   
```r
> sd_sal_edu = tapply(ex8$salary, ex8$edu, sd)
> sd_sal_edu
        1         2         3 
190.91883  61.84658  89.95369 
> rownames(sd_sal_edu) = c("A middle school graduate or lower", "A high school graduate","A college graduate or higher")
> sd_sal_edu
 A middle school graduate or lower     A high school graduate     A college graduate or higher 
190.91883                              61.84658                   89.95369 
```
   
```r
> sex_edu = list(ex8$sex, ex8$edu)
> tapply(ex8$salary, sex_edu, mean)
    1        2   3
1  NA 173.3333 310
2 235 290.0000 220
> mean_sal_sex_edu = tapply(ex8$salary, sex_edu, mean)
> mean_sal_sex_edu
    1        2   3
1  NA 173.3333 310
2 235 290.0000 220
> # 행 이름 지정
> # Name a row
> rownames(mean_sal_sex_edu) = c("M", "F")
> # 열 이름 지정
> # Name a column
> colnames(mean_sal_sex_edu) = c("Middle", "High", "College-")
> mean_sal_sex_edu
  Middle     High College-
M     NA 173.3333      310
F    235 290.0000      220
```
   
// NA = Not Available : 이런 경우가 없으므로 구할 수 없음   
- NA = Not Available : This is not the case, so it is not available   
   
<br />
### Obtaining Frequency Table and Division Table   
// 빈도표 및 분할표 구하기   
   
// 성별과 교육정도의 빈도표 및 분할표   
- Frequency table and division table of gender and education level   
   
```r
> table(ex8$sex)

1 2 
6 4 
> table(ex8$edu)

1 2 3 
2 4 4 
> sex_edu = table(ex8$sex, ex8$edu)
> sex_edu
   
    1 2 3
  1 0 3 3
  2 2 1 1
```
   
```r
> colnames(sex_edu) = c("A middle school graduate or lower", "A high school graduate", "A college graduate or higher")
> rownames(sex_edu) = c("Male ", "Female")
> sex_edu
    
          A middle school graduate or lower A high school graduate A college graduate or higher
  Male                                    0                      3                            3
  Female                                  2                      1                            1
```
   
```r
> summary(sex_edu)
Number of cases in table: 10 
Number of factors: 2 
Test for independence of all factors:
        Chisq = 3.75, df = 2, p-value = 0.1534
        Chi-squared approximation may be incorrect
```
   
<br />
## Draw a graph   
// 그래프 그리기   
   
<br />
### Bar Plot and Pie   
// 막대그림 및 원그림   
   
#### Bar Plots and Pie of edu variable   
// 교육 (edu) 변수의 막대그림 및 원그림   
   
```r
> edu_freq = table(ex8$edu)
> edu_freq

1 2 3 
2 4 4 
> rownames(edu_freq) = c("Middle", "High", "College-")
> # 막대그림
> # Bar Plot
> barplot(edu_freq)
> title("a bar plot of edu level")
> # 원그림
> # Pie
> pie(edu_freq)
> title("a circle plot of edu level")
> # pie(edu_freq, main="a cicle picture of edu level")
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRBarplot1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRBarplot2.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRPie1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRPie2.png)
   
#### Gender classification Bar Plot   
// 성별구분 막대그림   
   
// 성별 구분 교육 (edu) 변수의 막대그림   
- Bar Plot of gender classification edu variable   
   
```r
> sex_edu=table(ex8$sex, ex8$edu)
> sex_edu
   
    1 2 3
  1 0 3 3
  2 2 1 1
> colnames(sex_edu) = c("Middle", "High", "College-")
> rownames(sex_edu) = c("M", "F")
> # 막대그림
> # Bar Plot
> barplot(sex_edu)
> barplot(sex_edu, main="Gender education level bar chart")
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRBarplot3.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRBarplot4.png)
   
<br />
### Histogram, Stem-and-Leaf Plot, Box Plot   
// 히스토그램, 줄기-잎 그림, 상자그림   
   
```r
> # 히스토그램
> # Histogram
> hist(ex8$salary, nclass=4)
> # 줄기-잎 그림
> # Stem-and-Leaf Plot
> stem(ex8$salary)

  The decimal point is 2 digit(s) to the right of the |

  1 | 057    # 100, 150, 170
  2 | 0229    # 200, 220, 220, 290
  3 | 07    # 300, 370
  4 | 1    # 400

> # par는 한 화면을 분할해서 보여줌 : c(1, 2) == 행 1, 열 2
> # par is to split one screen and show it : c(1, 2) == row 1, column 2
> par(mfrow=c(1, 2))
> # 상자그림
> # Box Plot
> boxplot(ex8$salary~ex8$sex, main="box plot")
> # factor 이산형 변수의 범주를 알려줌
> # factor finds the range of discrete variables
> ex8$sex = factor(ex8$sex, levels=c(1:2), labels = c("M", "F"))
> boxplot(ex8$salary~ex8$sex, main="box plot2")
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRHist1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRBoxPlot1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRBoxPlot2.png)
   
<br />
### Continuous Data Graph : Stem-and-Leaf Plot   
// 연속형자료 그래프 : 줄기-잎 그림   
   
// 줄기-잎 그림 (stem-and-leaf plot)   
// - 분포의 대략적인 형태를 살펴보기 위하여 작성되는 그래프로 군집의 존재여부, 집중도가 높은 구간, 대칭성의 여부, 자료의 범위 및 산포, 특이값의 존재 여부 등을 파악하는데 이용됨   
- Stem-and-leaf plot   
  - It is a graph created to examine the approximate shape of the distribution and is used to determine the existence of clusters, sections with high concentration, symmetry, range and distribution of data, and the existence of singular values   
   
// 예시   
// - 점수자료   
- Example   
  - Score data   
    - `54 57 55 23 51 64 90 51 52 43 15 10 92 74 54 78 37 73 52 48 41 33 52 30 41 51 18 39 46 29 53 44 46 56 28 58 29 58 67 35 25 38 61 53 23 73 69 47 41 45 77 56 89 28 54 99 10 43 35 24 21 23 67 14 53`   
   
```r
> score = scan("c:/Users/Desktop/DataAnalysis_score.txt")
Read 65 items
> stem(score)

  The decimal point is 1 digit(s) to the right of the |

  1 | 00458
  2 | 1333458899
  3 | 0355789
  4 | 11133456678
  5 | 111222333444566788
  6 | 14779
  7 | 33478
  8 | 9
  9 | 029

```
   
```r
> stem(score, scale=2)

  The decimal point is 1 digit(s) to the right of the |

  1 | 004
  1 | 58
  2 | 13334
  2 | 58899
  3 | 03
  3 | 55789
  4 | 111334
  4 | 56678
  5 | 111222333444
  5 | 566788
  6 | 14
  6 | 779
  7 | 334
  7 | 78
  8 | 
  8 | 9
  9 | 02
  9 | 9

```
   
```r
> # 도움말
> # Help
> ?stem
httpd 도움말 서버를 시작합니다 ... 완료
```
   
<br />
### Graph of continuous data : Box plot   
// 연속형자료 그래프 : 상자그림   
   
```r
> summary(score)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
  10.00   33.00   48.00   47.62   57.00   99.00 
> boxplot(score)
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRBoxPlot3.png)
   
<br />
### Draw a scatter plot   
// 산점도 그리기   
   
#### Draw a scatter plot of (age, salary)   
// (age, salary) 산점도 그리기   
   
```r
> head(ex8, 3)
  id sex age edu salary
1  1   M  21   2    150
2  2   F  22   1    100
3  3   M  33   2    200
> # pch는 점의 모양
> # pch is the shape of a dot
> plot(ex8$age, ex8$salary, col="BLUE", pch=19)
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRScatterPlot1.png)
   
#### Draw a scatter plot by gender   
// 성별로 구분한 산점도 그리기   
   
```r
> plot(ex8$age, ex8$salary, type="n")
> # 해당하는 값만 표기
> # Mark corresponding values only
> points(ex8$age[ex8$sex==1], ex8$salary[ex8$sex==1], pch="M", col="BLUE")
> points(ex8$age[ex8$sex==2], ex8$salary[ex8$sex==2], pch="F", col="RED")
> # legend는 범례임
> legend("bottomright", legend=c("Male", "Female"), pch=c("M", "F"), col=c("BLUE", "RED"))
> # legend(locator(1), ~~~) try! # 마우스로 클릭한 위치에 범례를 표기
> # legend(locator(1), ~~~) try! # Mark legend at mouse-clicked locations
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRScatterPlot2.png)
   
```r
> # 도움말
> # Help
> ?legend
```
   
<br />
## R operation   
// R 연산   
   
<br />
### Scalar and Vector Operation   
// 스칼라와 벡터 연산   
   
#### Scalar Operation   
// 스칼라 연산   
   
```r
> x = 4
> y = 4*x + 7
> y
[1] 23
> x <-4
> y <-4*x + 7
> y
[1] 23
```
   
#### Vector Operation   
// 벡터 연산   
   
```r
> x = c(-10:10)
> y = 4*x + 7
> y
 [1] -33 -29 -25 -21 -17 -13  -9  -5  -1   3   7  11  15  19  23  27  31  35  39  43  47
> x[3]
[1] -8
> x[1:5]
[1] -10  -9  -8  -7  -6
> x1 = x[x<0]
> x1
 [1] -10  -9  -8  -7  -6  -5  -4  -3  -2  -1
> y = 4*x1 + 7
> y
 [1] -33 -29 -25 -21 -17 -13  -9  -5  -1   3
```
   
<br />
### Data frame   
   
```r
> x = c('red', 'green', 'blue')
> y = c(1,2,3)
> z = c(4,5,6)
> dframe= data.frame(x,y,z)
> dframe
      x y z
1   red 1 4
2 green 2 5
3  blue 3 6
> dframe[1,1]
[1] "red"
> dframe[1,2]
[1] 1
> names(dframe)
[1] "x" "y" "z"
> dframe$y
[1] 1 2 3
> dframe[,2]
[1] 1 2 3
```
   
<br />
### seq function : Create an object with a series of values   
// seq 함수 : 일련의 값을 갖는 객체를 생성   
   
```r
> x_seq = seq(-pi, pi,1)
> x_seq
[1] -3.1415927 -2.1415927 -1.1415927 -0.1415927  0.8584073  1.8584073  2.8584073
> round(x_seq, 4)
[1] -3.1416 -2.1416 -1.1416 -0.1416  0.8584  1.8584  2.8584
> x1_seq = seq(-pi, pi, length=10)
> x1_seq
 [1] -3.1415927 -2.4434610 -1.7453293 -1.0471976 -0.3490659  0.3490659  1.0471976  1.7453293  2.4434610  3.1415927
```
   
<br />
### Matrix operation   
// 행렬 연산   
   
#### Create a Matrix   
// 행렬 생성   
   
```r
> x = c(1:12)
> x = matrix(x, ncol=4, byrow=T)
> x
     [,1] [,2] [,3] [,4]
[1,]    1    2    3    4
[2,]    5    6    7    8
[3,]    9   10   11   12
```
   
#### Matrix with all element values the same constant   
// 모든 원소값이 동일한 상수인 행렬   
   
```r
> x = matrix(1, nrow=4, ncol=3)
> x
     [,1] [,2] [,3]
[1,]    1    1    1
[2,]    1    1    1
[3,]    1    1    1
[4,]    1    1    1
```
   
#### Submatrix extraction   
// 서브 행렬 추출   
   
```r
> x = c(1:12)
> x = matrix(x, ncol=4, byrow=T)
> x
     [,1] [,2] [,3] [,4]
[1,]    1    2    3    4
[2,]    5    6    7    8
[3,]    9   10   11   12
> x[,c(1:3)]
     [,1] [,2] [,3]
[1,]    1    2    3
[2,]    5    6    7
[3,]    9   10   11
> x[c(1:3), -2]
     [,1] [,2] [,3]
[1,]    1    3    4
[2,]    5    7    8
[3,]    9   11   12
```
   
#### Matrix operation function   
// 행렬 연산 함수   
   
// ncol(x) : 열의 수   
// nrow(x) : 행의 수   
// t(x) : 전치행렬   
// cbind(...) : 열을 더할 때 이용되는 함수   
// rbind(...) : 행을 더할 때 이용되는 함수   
// diag(x) : 대각행렬   
// apply(x,m,fun) : 행 또는 열에 함수 적용   
// x %*% y : 두 행렬의 곱   
// solve(x) : 역행렬   
- ncol(x) : Number of columns   
- nrow(x) : Number of rows   
- t(x) : Transpose matrix   
- cbind(...) : Functions used to add columns   
- rbind(...) : Functions used to add rows   
- diag(x) : Diagonal matrix   
- apply(x,m,fun) : Apply a function to a row or column   
- x %*% y : Multiplication of two matrices   
- solve(x) : Inverse matrix   
   
#### Example of matrix multiplication and apply functions   
// 행렬의 곱 및 apply 함수 예시   
   
```r
> x = c(1,2,3,5,6,7)
> x = matrix(x, ncol=3, byrow=T)
> x
     [,1] [,2] [,3]
[1,]    1    2    3
[2,]    5    6    7
> y <- c(1:4)
> y <- matrix(y, ncol=2)
> y
     [,1] [,2]
[1,]    1    3
[2,]    2    4
> t(x) %*% y
     [,1] [,2]
[1,]   11   23
[2,]   14   30
[3,]   17   37
> apply(x, 1, mean)  # 1: row
[1] 2 6
> apply(x, 2, mean)  # 2 : column
[1] 3 4 5
```
   
<br />
## Function statement   
// Function 문   
   
// 자주 쓰이는 계산 등은 function 문으로 작성하는 것이 좋음   
- It is recommended to fill out frequently used calculations with function statements   
   
<br />
### Example 1   
// 예시 1   
   
// 제곱값을 반환하는 함수   
- Functions that return squared values   
   
```r
> sq_value <- function(x) {x*x}
> sq_value(4)
[1] 16
```
   
<br />
### Example 2   
// 예시 2   
   
// power 값을 반환하는 함수   
- Functions that return a power value   
   
```r
> fpower <- function(x, n){x^n}
> fpower(3, 2)
[1] 9
> fpower(4, 1/2)
[1] 2
```
   
<br />
### Example 3   
// 예시 3   
   
// 여러 개의 power 값을 동시에 반환하는 함수   
- Function that returns multiple power values at the same time   
   
```r
> power_value <- function(x, n1, n2, n3=5)
+ {n1_val = x^n1
+ n2_val = x^n2
+ n3_val = x^n3
+ value = list(v1=n1_val, v2=n2_val, v3=n3_val)
+ return(value)
+ }
> power_value(2, 1/2, 2)
$v1
[1] 1.414214

$v2
[1] 4

$v3
[1] 32
```
   
<br />
### Example 4   
// 예시 4   
   
// 외부 파일을 불러와서 실행하는 경우   
- A case of importing and executing an external file   
   
#### Create and save 'DataAnalysis_powerfun.r' file   
// 'DataAnalysis_powerfun.r' 파일 작성 및 저장   
   
```r
power_value <- function(x, n1, n2, n3=7)
{n1_val = x^n1
 n2_val = x^n2
 n3_val = x^n3
 value = list(v1=n1_val, v2=n2_val, v3=n3_val)
 return(value)
}
```
   
#### Import and use the file 'DataAnalysis_powerfun.r'   
// 'DataAnalysis_powerfun.r' 파일 불러와서 사용   
   
```r
> source("c:/Users/Desktop/DataAnalysis_powerfun.r")
> power_value(2, 1/2, 2)
$v1
[1] 1.414214

$v2
[1] 4

$v3
[1] 128
```
   
<br />
## Normal distribution   
// 정규분포   
   
<br />
### Draw Normal distribution   
// 정규분포 그리기   
   
// '-3 ~ 3'사이의 정규분포   
- Normal distribution between '-3 and 3'   
   
```r
plot(function(x) dnorm(x), -3, 3, main="Normal distribution")
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRPlot1.png)
   
// Pr(X ≤ x) 구하기   
- Calculate Pr(X ≤ x)   
   
```r
> # 0이하의 값 : Pr(X < 0)
> # A value less than or equal to zero : Pr(X < 0)
> pnorm(0)
[1] 0.5
> # 1이하의 값 : Pr(X < 1)
> # A value of not more than 1 : Pr(X < 1)
> pnorm(1)
[1] 0.8413447
> # 3이하의 값 : Pr(X < 3)
> # A value of not more than 3 : Pr(X < 3)
> pnorm(3)
[1] 0.9986501
```
   
<br />
### Creating a normal distribution random number   
// 정규분포 난수 (random number) 생성   
   
// 정규분포를 따르는 난수 생성 : rnorm 함수 이용   
- Creating a random number with a normal distribution : Using the rnorm function   
   
#### Example 1   
// 예시 1   
   
// 평균이 0, 표준편차가 1인 정규분포를 따르는 난수 20개를 생성   
- Create 20 random numbers that follow a normal distribution with a mean of 0 and a standard deviation of 1   
   
```r
> rnorm(20)
 [1] -0.20466334  1.71301903 -0.07705695 -1.39869328 -0.01477581 -0.62244906
 [7] -1.54302459  0.40840684  0.38027117 -1.31104111  0.79681746  0.86725790
[13]  1.39191488 -2.86480949  0.85967097  0.96426251  0.58113044  1.12866478
[19]  2.38094192  0.31659873
```
   
// 평균이 0, 표준편차가 1인 정규분포를 따르는 난수 100개를 생성   
- Create 100 random numbers that follow a normal distribution with a mean of 0 and a standard deviation of 1   
   
```r
> ran_norm = rnorm(100)
> mean(ran_norm)
[1] 0.06679363
> sd(ran_norm)
[1] 1.038717
> hist(ran_norm)
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRNorm1.png)
   
#### Example 2   
// 예시 2   
   
// 평균이 -5 이고, 표준편차가 2.5인 정규분포를 따르는 난수 100개 생성   
- Create 100 random numbers that follow a normal distribution with a mean of -5 and a standard deviation of 2.5   
   
```r
> ran_norm = rnorm(100, -5, 2.5)
> mean(ran_norm)
[1] -4.985383
> sd(ran_norm)
[1] 2.455149
> hist(ran_norm)
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRNorm2.png)
   
<br />
## Draw a discrete graph   
// 이산형 그래프 그리기   
   
<br />
### Example   
// 예시   
   
// 세 그룹 (C1, C2, C3) 이 다섯 자선단체 (T1, T2, T3, T4, T5) 에 기부하는 다음 가상자료를 이용하여 막대그림, 원그림을 그려보시오   
- Draw a bar plot or pie using virtual data donated by three groups (C1, C2, C3) to five charities (T1, T2, T3, T4, T5)   
   
||C1|C2|C3|
|:---:|:---:|:---:|:---:|
|T1|5.4|3.1|3.5|
|T2|5.7|8.6|25.0|
|T3|20.4|26.0|22.0|
|T4|36.3|34.1|28.0|
|T5|14.4|11.4|4.5|
   
#### Read data   
// 데이터 읽기   
   
```r
> percData <- read.table("c:/Users/Desktop/DataAnalysis_perc.txt", header=T)
> percData <- as.matrix(percData)
> var_name <- colnames(percData)
> case_name <- rownames(percData)
> percData
     C1   C2   C3
T1  5.4  3.1  3.5
T2  5.7  8.6 25.0
T3 20.4 26.0 22.0
T4 36.3 34.1 28.0
T5 14.4 11.4  4.5
```
   
#### Draw Bar Plots   
// 막대그림 그리기   
   
// 겹침 막대그림 그리기   
// - 범례는 원하는 위치에 그리기   
- Draw overlapping Bar Plots   
  - The legend is drawn in the desired position   
   
```r
> barplot(percData, names=var_name)
> legend(locator(1), case_name)
> title("Barplot")
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRBarplot5.png)
   
#### Draw Pie   
// 원그림 그리기   
   
// 첫번째 열에 대한 원그림 그리기   
// - 각 항목에 대한 이름 지정   
- Draw a pie for the first column   
  - Specify a name for each item   
   
```r
> pie(percData[,1], labels=case_name)
> title("Pie Chart of Company 1")
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRPie3.png)
   
<br />
### Open and close multiple devices   
// 디바이스를 여러개 열고, 닫기   
   
```r
> dev.new()
> dev.off()
windows 
      2 
```
   
<br />
## Draw a Continuous Graph   
// 연속형 그래프 그리기   
   
<br />
### Draw a Box plot   
// 상자그림 그리기   
   
// 예시   
// - percData의 세 회사 (C1, C2, C3) 상자그림 그리기   
- Example   
  - Draw the three companies (C1, C2, C3) box plots of perData   
   
```r
> percData <- read.table("c:/Users/Desktop/DataAnalysis_perc.txt", header=T)
> percData <- as.matrix(percData)
> var_name <- colnames(percData)
> case_name <- rownames(percData)
> percData
     C1   C2   C3
T1  5.4  3.1  3.5
T2  5.7  8.6 25.0
T3 20.4 26.0 22.0
T4 36.3 34.1 28.0
T5 14.4 11.4  4.5
> boxplot(percData[, 1], percData[, 2], percData[, 3], names=var_name)
> title("Box Plot")
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRBoxPlot4.png)
   
<br />
### Stem-and-Leaf Plot and Histogram   
// 줄기-잎 그림 및 히스토그램   
   
// 예시   
// - 자유도가 5인 t-분포를 따르는 난수 50개를 만들어 히스토그램 및 줄기-잎 그림 그리기   
// -- t-분포를 따르는 난수 생성 : rt 함수 이용   
- Example   
  - Create 50 random numbers along t-distributions with degrees of freedom of 5 to draw histogram and stem-and-leaf plot   
    - Creating random numbers along t-distribution : Using the rt function   
   
```r
> my_sample <- rt(50, 5)
> my_sample
 [1]  0.470967420  2.872577613 -0.189839369 -0.990848571  1.458373807
 [6]  0.039597513  0.006365191  1.730107942  1.414380279  1.116257724
[11] -1.052647606 -0.050180943 -0.563077765 -0.443550067  0.584313897
[16]  0.149195306  0.523952673  0.412605980 -0.341819082  1.712666952
[21] -1.064514016 -1.994999874  0.331202765 -1.745964794 -1.133480438
[26] -1.420352494 -1.284921105  0.621853179  0.137510971 -2.240698108
[31]  1.846250407 -0.022672888 -0.279845250 -1.703540655  0.488480851
[36] -0.256673572 -0.238409561  1.285860759  2.408410474  0.442952052
[41] -0.943142780  0.815065133 -1.090240406 -0.305578428 -2.488182424
[46] -1.092565288  0.854350203 -0.842589308 -0.904285859  0.876080961
```
   
```r
hist(my_sample)
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRHist2.png)
   
```r
> stem(my_sample)

  The decimal point is at the |

  -2 | 520
  -1 | 7743111110
  -0 | 9986433332210
   0 | 001134455566899
   1 | 1345778
   2 | 49
```
   
<br />
### Time series plot   
// 시계열 그림   
   
// 예시   
// - R 시스템에 내장된 데이터 co2를 이용한 시계열 그림 그리기   
// -- co2는 연도별 이산화탄소 정보   
- Example   
  - Drawing a time series plot using the data co2 embedded in the R system   
    - co2 is CO2 information by year   
   
```r
> co2
        Jan    Feb    Mar    Apr    May    Jun    Jul    Aug    Sep    Oct    Nov    Dec
1959 315.42 316.31 316.50 317.56 318.13 318.00 316.39 314.65 313.68 313.18 314.66 315.43
1960 316.27 316.81 317.42 318.87 319.87 319.43 318.01 315.74 314.00 313.68 314.84 316.03
1961 316.73 317.54 318.38 319.31 320.42 319.61 318.42 316.63 314.83 315.16 315.94 316.85
1962 317.78 318.40 319.53 320.42 320.85 320.45 319.45 317.25 316.11 315.27 316.53 317.53
1963 318.58 318.92 319.70 321.22 322.08 321.31 319.58 317.61 316.05 315.83 316.91 318.20
1964 319.41 320.07 320.74 321.40 322.06 321.73 320.27 318.54 316.54 316.71 317.53 318.55
1965 319.27 320.28 320.73 321.97 322.00 321.71 321.05 318.71 317.66 317.14 318.70 319.25
1966 320.46 321.43 322.23 323.54 323.91 323.59 322.24 320.20 318.48 317.94 319.63 320.87
1967 322.17 322.34 322.88 324.25 324.83 323.93 322.38 320.76 319.10 319.24 320.56 321.80
1968 322.40 322.99 323.73 324.86 325.40 325.20 323.98 321.95 320.18 320.09 321.16 322.74
1969 323.83 324.26 325.47 326.50 327.21 326.54 325.72 323.50 322.22 321.62 322.69 323.95
1970 324.89 325.82 326.77 327.97 327.91 327.50 326.18 324.53 322.93 322.90 323.85 324.96
1971 326.01 326.51 327.01 327.62 328.76 328.40 327.20 325.27 323.20 323.40 324.63 325.85
1972 326.60 327.47 327.58 329.56 329.90 328.92 327.88 326.16 324.68 325.04 326.34 327.39
1973 328.37 329.40 330.14 331.33 332.31 331.90 330.70 329.15 327.35 327.02 327.99 328.48
1974 329.18 330.55 331.32 332.48 332.92 332.08 331.01 329.23 327.27 327.21 328.29 329.41
1975 330.23 331.25 331.87 333.14 333.80 333.43 331.73 329.90 328.40 328.17 329.32 330.59
1976 331.58 332.39 333.33 334.41 334.71 334.17 332.89 330.77 329.14 328.78 330.14 331.52
1977 332.75 333.24 334.53 335.90 336.57 336.10 334.76 332.59 331.42 330.98 332.24 333.68
1978 334.80 335.22 336.47 337.59 337.84 337.72 336.37 334.51 332.60 332.38 333.75 334.78
1979 336.05 336.59 337.79 338.71 339.30 339.12 337.56 335.92 333.75 333.70 335.12 336.56
1980 337.84 338.19 339.91 340.60 341.29 341.00 339.39 337.43 335.72 335.84 336.93 338.04
1981 339.06 340.30 341.21 342.33 342.74 342.08 340.32 338.26 336.52 336.68 338.19 339.44
1982 340.57 341.44 342.53 343.39 343.96 343.18 341.88 339.65 337.81 337.69 339.09 340.32
1983 341.20 342.35 342.93 344.77 345.58 345.14 343.81 342.21 339.69 339.82 340.98 342.82
1984 343.52 344.33 345.11 346.88 347.25 346.62 345.22 343.11 340.90 341.18 342.80 344.04
1985 344.79 345.82 347.25 348.17 348.74 348.07 346.38 344.51 342.92 342.62 344.06 345.38
1986 346.11 346.78 347.68 349.37 350.03 349.37 347.76 345.73 344.68 343.99 345.48 346.72
1987 347.84 348.29 349.23 350.80 351.66 351.07 349.33 347.92 346.27 346.18 347.64 348.78
1988 350.25 351.54 352.05 353.41 354.04 353.62 352.22 350.27 348.55 348.72 349.91 351.18
1989 352.60 352.92 353.53 355.26 355.52 354.97 353.75 351.52 349.64 349.83 351.14 352.37
1990 353.50 354.55 355.23 356.04 357.00 356.07 354.67 352.76 350.82 351.04 352.69 354.07
1991 354.59 355.63 357.03 358.48 359.22 358.12 356.06 353.92 352.05 352.11 353.64 354.89
1992 355.88 356.63 357.72 359.07 359.58 359.17 356.94 354.92 352.94 353.23 354.09 355.33
1993 356.63 357.10 358.32 359.41 360.23 359.55 357.53 355.48 353.67 353.95 355.30 356.78
1994 358.34 358.89 359.95 361.25 361.67 360.94 359.55 357.49 355.84 356.00 357.59 359.05
1995 359.98 361.03 361.66 363.48 363.82 363.30 361.94 359.50 358.11 357.80 359.61 360.74
1996 362.09 363.29 364.06 364.76 365.45 365.01 363.70 361.54 359.51 359.65 360.80 362.38
1997 363.23 364.06 364.61 366.40 366.84 365.68 364.52 362.57 360.24 360.83 362.49 364.34
```
   
```r
> plot(co2)
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRPlot2.png)
   
```r
> lines(smooth(co2), col="BLUE")
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRPlot3.png)
   
<br />
### Draw a function   
// 함수 그리기   
   
#### Draw a mathematical function graph   
// 수학 함수 그래프 그리기   
   
// '-30 ~ 30' 사이의 일련의 수를 0.1 간격으로 x에 값 생성   
// x의 각 값에 대응하는 y 값 생성 : `y = f(x)`   
// `plot()` 함수의 `type="l"` 은 라인으로 그리라는 의미임   
// `abline()` 은 가로 / 세로 축을 그림. `lty=2` 는 라인타입을 2로 그리라는 의미임   
- Create a series of numbers between '-30 and 30' as values on x at 0.1 intervals   
- Create a y value corresponding to each value of x : `y = f(x)`   
- The `type="l"` of the `plot()` function means to draw a line   
- `abline()` illustrates the horizontal/vertical axis. `lty=2` means draw line type 2   
   
```r
> x = seq(-30, 30, 0.1)
> y = 2*(x-3)^3 + (x-2)^2 + 4*x -3
> plot(x, y, type="l")
> abline(h=0, v=0, lty=2)
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRFunction1.png)
   
<br />
### Draw a histogram   
// 히스토그램 그리기   
   
// 예시   
// - co2 히스토그램 그리기   
- Example   
  - Draw a co2 histogram   
   
```r
> co2Hist = hist(co2)
> names(co2Hist)
[1] "breaks"   "counts"   "density"  "mids"     "xname"    "equidist"
> co2Hist$breaks
 [1] 310 315 320 325 330 335 340 345 350 355 360 365 370
> co2Hist$counts
 [1]  8 62 65 52 46 40 39 37 41 45 28  5
> co2Hist$mids
 [1] 312.5 317.5 322.5 327.5 332.5 337.5 342.5 347.5 352.5 357.5 362.5 367.5
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRHist3.png)
   
<br />
### Draw Stem-and-Leaf Plot by Group   
// 그룹별 줄기-잎 그림 그리기   
   
// 예시   
// - 자료에서 남녀 (sex) 별로 변수 age 줄기-잎 그림 그리기, 그룹별 줄기-잎 그림 비교 그리기   
- Example   
  - Draw a variable age stem-and-leaf plot for each male and female (sex) in the data, and draw a comparison of stem-and-leaf plots by group   
   
```r
> ex8
   id sex age edu salary
1   1   1  21   2    150
2   2   2  22   1    100
3   3   1  33   2    200
4   4   2  33   3    220
5   5   1  28   2    170
6   6   1  41   3    300
7   7   2  39   2    290
8   8   1  32   3    220
9   9   2  44   1    370
10 10   1  55   3    410
> stem(ex8$age[ex8$sex==1])

  The decimal point is 1 digit(s) to the right of the |

  2 | 18
  3 | 23
  4 | 1
  5 | 5

> stem(ex8$age[ex8$sex==2])

  The decimal point is 1 digit(s) to the right of the |

  2 | 2
  2 | 
  3 | 3
  3 | 9
  4 | 4

> library(aplpack)
> m_age = ex8$age[ex8$sex==1]
> f_age = ex8$age[ex8$sex==2]
> stem.leaf.backback(m_age, f_age)
________________________
  1 | 2: represents 12, leaf unit: 1 
    m_age      f_age
________________________
   1    1| 2* |2    1   
   2    8| 2. |         
  (2)  32| 3* |3   (1)  
         | 3. |9   (1)  
   2    1| 4* |4    1   
         | 4. |         
         | 5* |         
   1    5| 5. |         
         | 6* |         
________________________
n:      6      4    
________________________
```
   
<br />
### Draw a box plot by group   
// 그룹별 상자그림 그리기   
   
// 예시   
// - 자료에서 남녀 (sex) 별로 변수 age 상자그림 비교 그리기   
- Example   
  - Draw a comparison of variable age box plots by male and female (sex) in the data   
   
```r
> boxplot(age ~ sex, data=ex8)
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRBoxPlot5.png)
   
<br />
### Draw a group comparison scatter plot   
// 그룹비교 산점도 그리기   
   
// 예시   
// - 자료에서 남녀 (sex) 별로 구분한 (나이, 월수입) 산점도 그리기   
- Example   
  - Draw a scatter plot (age, monthly income) divided by male and female (sex) in the data   
   
```r
> plot(ex8$age, ex8$salary)
> points(ex8$age[ex8$sex==1], ex8$salary[ex8$sex==1], pch="M", col=4)
> points(ex8$age[ex8$sex==2], ex8$salary[ex8$sex==2], pch="F", col=2)
> legend("bottomright", legend=c("Male", "Femail"), pch=c("M", "F"), col=c("BLUE", "RED"))
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRPlot4.png)
   
```r
> plot(ex8$age, ex8$salary)
> points(ex8$age[ex8$sex==1], ex8$salary[ex8$sex==1], pch=19, col=4)
> points(ex8$age[ex8$sex==2], ex8$salary[ex8$sex==2], pch=17, col=2)
> legend("bottomright", legend=c("Male", "Femail"), pch=c(19, 17), col=c(4, 2))
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisRPlot5.png)
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
