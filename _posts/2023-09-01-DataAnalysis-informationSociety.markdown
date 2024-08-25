---
layout: post
title:  "Introduction to Data Analysis: Information society, computer and software"
date:   2023-09-01 09:00:00 +0900
categories: [Data Analysis]
---

## Information society - Knowledge informatization   
   
- The era of Big Data, Deep Learning, and AI (Artificial Intelligence)   
- A society where society and economy move around information.   
- A society that cannot survive without collecting and analyzing information and making accurate decisions.   
- A society in which information rapidly increases, grows, and is disseminated.   
- In an information society, efficient collection of information, judgment of the value of the collected information, and the ability to utilize information are essential. In this sense, it is now called a knowledge information society.   
- In order to efficiently process and analyze data in the knowledge and information society, the ability to use computers and analyze data is essential.   
   
<br />
### Essential requirements in a knowledge information society   
   
- Must know how to use a computer.   
- Enables efficient use of the internet.   
- Statistical (logical) thinking is required to properly understand information, identify problems, and make decisions.   
- Familiarize yourself with the basic concepts and methodologies of data analysis.   
- Make good use of data analysis software to extract useful information from data and make rational decisions.   
   
<br />
## Data analysis overview   
   
<br />
### Data analysis procedure   
   
- Step 1. Definition of the problem   
  - Research usually begins with simple and vague questions.   
  - Definition of the problem is to specify this as a detailed and accurate question and make it the purpose of research.   
  - A detailed review should be made of what population is the subject of research, what the uncertainties are, and what decisions can be made.   
- Step 2. Planning of investigation and experiment   
  - Statistical Survey Methodology, Sample Survey Theory, Experimental design and application   
  - Once the purpose of the research is clearly defined, an achievable investigation or experiment must be planned.   
  - Specifically, decide whether to survey the entire population being studied or only a sample.   
  - If you are going to conduct a sample study, you must decide how to select the sample, what size the sample should be, and what data to obtain from each sample.   
- Step 3. Collection of data   
  - When a specific investigation or experiment is planned, data is collected accordingly.   
  - In some cases, data have already been collected or can be easily obtained from the Internet or literature. In this case, it is necessary to review whether these data are appropriate and accurate for the research purpose.   
  - Collecting data yourself is usually a very complex and difficult task that requires a lot of time and money, and is prone to errors.   
  - In some cases, it may be impossible to collect data as planned, and in other cases, the collected data may not be appropriate for the research purpose.   
  - To reduce these problems, preliminary data may be collected first and the data collection plan may be revised or supplemented.   
- Step 4. Organizing and analyzing data   
  - After collecting appropriate data, organize the data using charts or pictures.   
  - In addition, data are analyzed using analysis methods appropriate for solving a given problem.   
  - Utilization of data analysis systems: Excel, R, Python, SAS, SPSS, Minitab, etc.   
  - Statistical methods: Statistical introduction, R computing, excel data analysis, descriptive statistics, exploratory data analysis, categorical data analysis, comparison of two population groups, regression analysis, regression model, experimental design, multivariate analysis, etc.   
- Step 5. Evaluation of analysis results   
  - The analyzed results are used to draw conclusions about the questions raised for the purpose of the research.   
  - In some cases, only partial answers may be concluded, and in other cases, conclusions may be drawn about questions that were not raised.   
  - Suggestions for various new studies can also be made based on the conclusions.   
   
<br />
### Types of data analysis software   
   
- Excel   
- SPSS   
  - www.spss.co.kr   
  - GUI (Graphic User Interface)   
  - Various dialog boxes are provided to suit the analysis procedure, allowing for easy analysis processing.   
  - Familiar to general users with data input in spreadsheet format.   
  - Provides statistical analysis procedures using both menu and program methods.   
  - Excellent statistical graphics function using menu method.   
  - It is possible to obtain a certificate of 'Social Research Analyst'.   
- SAS   
  - www.sas.com   
  - It's a program processing method.   
  - Excellent data processing capabilities   
  - Excellent functions such as database and data warehousing   
  - Various statistical analysis procedures   
  - Excellent data mining function   
  - Big data solution features   
  - It is possible to obtain a certificate of 'Social Research Analyst'.   
- R   
  - www.r-project.org   
  - Free   
  - Highly functional.   
  - It's a program processing method.   
  - Excellence in data processing, analysis, and graphics.   
- Python   
  - www.anaconda.com   
  - Free   
  - Object-oriented language   
  - Program grammar is easy.   
  - Excellent features for machine learning and deep learning.   
   
<br />
### SAS Module   
   
`SAS/BASE` : SAS Basic   
`SAS/STAT` : Data analysis and statistical analysis   
`SAS/AF` : Application development support   
`SAS/ASSIST` : Menu-type SAS system support   
`SAS/ETS` : Time Series Analysis   
`SAS/GRAPH` : Graph   
`SAS/IML` : Matrix Operation   
`SAS/INSIGHT` : Statistical analysis and graphic implementation   
`SAS/OR` : Operation Research   
`SAS/QC` : Statistical quality control   
`SAS/E-Miner` : Data Mining   
   
<br />
### R sample   
   
```r
> math = c(66, 63, 48, 46, 78, 60, 90, 50, 66, 70)
> physics = c(70, 68, 46, 48, 84, 64, 92, 52, 68, 72)
# Correlation coefficient
> cor(math, physics)
[1] 0.9907909
# scatter plot
> plot(math, physics, pch=16, col="BLUE", main="(math, physics scatterplot)")
# Regression equation
> abline(lm(physics ~ math))
# Check each point case.
> identify(math, physics)
[1] 5 7
```
   
```r
# Insert from 1 to 10 in a.
> a <- c(1:10)
# Divide all elements of a by 3.
> a/3
 [1] 0.3333333 0.6666667 1.0000000 1.3333333 1.6666667 2.0000000 2.3333333
 [8] 2.6666667 3.0000000 3.3333333
```
   
```r
# Importing file
> ex12 <- read.csv("C:/Users/R-workspace/ex1-2.csv")
# Check the contents of the file.
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
# scatter plot
> plot(ex12$math, ex12$physics, pch=19, col="BLUE")
# Change the title of the scatterplot.
> title("\n Scatter Plot of (math, physics)\n")
# Correlation coefficient
> cor(ex12$math, ex12$physics)
[1] 0.9693012
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
   
<br />
<cite>Source: Department of Computer Science, Korea National Open University</cite>
