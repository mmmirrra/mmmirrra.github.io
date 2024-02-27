---
layout: post
title:  "Introduction to Data Analysis: Information Society, Computer and Software"
date:   2024-02-26 09:00:00 +0900
categories: [DataAnalysis]
---

### Information Society - Knowledge Informatization   
- Big Data, Deep Learning, AI(Artificial Intelligence)   
- Computer utilization and data analytics capabilities are essential to efficiently process and analyze data   
- Statistical (logical) thinking required   
- Data analytics software needs to be well utilized   
   
### Data Analysis Procedure   
// 1. 문제의 정의   
// 2. 조사, 실험의 계획 : 통계조사방법론, 표본조사론, 실험계획과 응용   
// 3. 데이터의 수집   
// 4. 데이터의 정리, 분석 : R 컴퓨팅, 엑셀 데이터 분석, 통계학개론, 회귀모형, 다변량분석   
// 5. 분석결과의 평가   
1. Definition of the problem   
2. Investigation and experiment planning : Statistical Survey Methodology, Sample Survey Theory   
3. Collecting data   
4. Organizing and analyzing data : R Computing, Excel Data Analysis, Statistical Introduction, Regression Model, Multivariate Analysis   
5. Evaluation of analysis results   
   
### Data Analysis Software Types   
- Excel   
- SPSS   
  - www.spss.co.kr   
  - GUI(Graphic User Interface)   
  - Enter data in the form of a Spreadsheet   
  - Superior statistical graphics using the menu method   
  - It is possible to obtain a certificate of '사회조사분석사'   
- SAS   
  - www.sas.com   
  - It's a program processing method   
  - Data processing is excellent   
  - Excellent database, data warehousing, etc   
  - Data mining is excellent   
  - Big Data Solution Capabilities   
  - It is possible to obtain a certificate of '사회조사분석사'   
- R   
  - www.r-project.org   
  - Free   
  - highly functional   
  - It's a program processing method   
  - Excellence in data processing, analysis, and graphics   
- Python   
  - www.anaconda.com   
  - Free   
  - object-oriented language   
  - program grammar is easy   
  - Excellent features for machine learning and deep learning   
   
### SAS Module   
// SAS 기본   
`SAS/BASE` : SAS Basic   
// 자료의 분석 및 통계 분석   
`SAS/STAT` : Analysis and Statistical Analysis of Data   
// 응용 프로그램 개발 지원   
`SAS/AF` : Application Development Support   
// 메뉴 형식의 SAS 시스템 지원   
`SAS/ASSIST` : Supports SAS systems in menu format   
// 시계열 분석   
`SAS/ETS` : Time Series Analysis   
// 그래프   
`SAS/GRAPH` : Graph   
// 행렬 연산   
`SAS/IML` : Matrix operation   
// 통계분석 및 그래픽 구현   
`SAS/INSIGHT` : Stat and Graphics Implementation   
// 운영연구   
`SAS/OR` : Operation Research   
// 통계적 품질관리   
`SAS/QC` : Statistical Quality Control   
// 데이터마이닝   
`SAS/E-Miner` : Data Mining   
   
### R sample   
```
# 수학점수
> math = c(66, 63, 48, 46, 78, 60, 90, 50, 66, 70)
# 물리점수
> physics = c(70, 68, 46, 48, 84, 64, 92, 52, 68, 72)
# 상관계수
# Correlation coefficient
> cor(math, physics)
[1] 0.9907909
# 산점도
# scatter plot
> plot(math, physics, pch=16, col="BLUE", main="(math, physics scatterplot)")
# 회귀식
# Regression equation
> abline(lm(physics ~ math))
# 각 포인트 케이스 확인
# Check each point case
> identify(math, physics)
[1] 5 7
```
   
```
# Insert from 1 to 10 in a
> a <- c(1:10)
# Divide all elements of a by 3
> a/3
 [1] 0.3333333 0.6666667 1.0000000 1.3333333 1.6666667 2.0000000 2.3333333
 [8] 2.6666667 3.0000000 3.3333333
```
   
```
# Importing file
> ex12 <- read.csv("C:/Users/R-workspace/ex1-2.csv")
# Check the contents of the file
> head(ex12)
  id math physics
1  1   66      79
2  2   64      68
3  3   48      46
4  4   46      48
5  5   78      84
6  6   60      64
# data frame
> head(ex12, 3)
  id math physics
1  1   66      79
2  2   64      68
3  3   48      46
# 산점도
# scatter plot
> plot(ex12$math, ex12$physics, pch=19, col="BLUE")
# Change the title of the scatterplot
> title("\n Scatter Plot of (math, physics)\n")
# 상관계수
# Correlation coefficient
> cor(ex12$math, ex12$physics)
[1] 0.9693012
# 상관계수 검증
# Correlation coefficient verification
> cor.test(ex12$math, ex12$physics)

	Pearson's product-moment correlation

data:  ex12$math and ex12$physics
t = 7.8845, df = 4, p-value = 0.001399
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 0.7393390 0.9967622
sample estimates:
      cor 
0.9693012 
```
