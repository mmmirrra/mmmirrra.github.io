---
layout: post
title:  "Python: Control Structure"
date:   2024-05-09 09:00:00 +0900
categories: [Python]
---

### Understanding the Control Structure   
// 제어구조의 이해   
   
#### Structural Programming Paradigm   
// 구조적 프로그래밍 패러다임   
   
// 네덜란드의 컴퓨터 과학자인 에츠허르 비버 데이크스트라 (Edsger Wybe Dijkstra) 가 처음으로 제안   
// 절차적 프로그래밍 패러다임의 하위 개념   
// goto 문을 사용하지 않고 프로그램을 3가지 제어 구조만으로 구성하는 프로그램 패러다임   
// - 순차 (sequence) 구조   
// - 선택 (selection) 구조   
// - 반복 (iteration) 구조   
// 프로그램 실행 흐름이 간결하고 작은 규모로 조직화하기 쉬움   
- First proposed by a Dutch computer scientist, Edsger Wybe Dijkstra   
- Subconcepts of procedural programming paradigm   
- Program paradigm that consists of only three control structures without the use of goto statements   
  - Sequence structure   
  - Selection structure   
  - Iteration structure   
- Simplified program execution flow, easy to organize on a small scale   
   
<br />
### Sequence structure   
// 순차 구조   
   
// 실행의 흐름을 주어지는 명령의 위치적 흐름에 따라 수행하는 구조   
// - 명령 라인 위에서 아래로 흐르는 가장 직관적인 구조   
// - 일단 첫 단계를 시작하면 마지막 단계까지 수행함   
- A structure in which execution flows are carried out according to the positional flows of commands that are given   
  - The most intuitive structure that flows from top to bottom of the command line   
  - The sequential structure is carried out until the last step once the first step starts   
   
<br />
### Python practice   
// 파이썬 실습   
   
// 삼각형 모양으로 *을 출력하는 프로그램 작성하기   
- Create a program that outputs * in the shape of a triangle   
   
- Example   
   
```python
print("*")
print("***")
print("*****")
print("*******")
```
   
- Result   
   
```
*
***
*****
*******
```
   
- Example   
   
```python
print("   *")
print("  ***")
print(" *****")
print("*******")
```
   
- Result   
   
```
   *
  ***
 *****
*******
```
   
<br />
### User input   
// 사용자 입력   
   
// input : 사용자로부터 데이터를 입력받는 함수   
// - 입력 데이터를 문자 데이터 타입으로 반환 (사용자 입력을 통해 받아들인 데이터는 전부 문자형으로 들어옴)   
// - 함수의 파라미터는 입력 안내문의 목적으로 사용함   
- input : Function to receive data from the user   
  - Returns input data as a character data type (All data received through user input comes in character type)   
  - The parameters of the function are used for the purposes of the input guide   
   
- Example   
   
```python
rad = input("Enter a value for the radius : ")
```
   
- Result   
   
```
Enter a value for the radius : 30 [Enter]
```
   
// 원뿔 계산 프로그램 개선   
// - 원뿔의 부피 & 겉넓이 계산 프로그램   
// -- 부피 = 1/3πr²h   
// -- 겉넓이 = πr² + πrh   
// - 사용자로부터 반지름과 높이를 입력받고 계산   
- Improvement of the cone calculation program   
  - Calculation program for volume & surface area of cone   
    - Volume = 1/3πr²h   
    - Surface area = πr² + πrh   
  - Receive and calculate the radius and height from the user   
   
```python
# 반지름, 높이 값 할당
# Assign radius, height value
rad = int(input("Enter a value for the radius : "))
hei = int(input("Enter a value for the height : "))
# 부피 출력
# Volume Output
vol = 1 / 3 * 3.14 * rad ** 2 * hei
# 겉넓이 출력
# Surface area Output
suf = 3.14 * rad ** 2 + 3.14 * rad * hei
print("The value of the volume is ", vol, sep="")
print("The value of the surface area is ", suf, sep="")
```
   
- Result   
   
```
Enter a value for the radius : 20 [Enter]
Enter a value for the height : 30 [Enter]
The value of the volume is 12559.999999999998
The value of the surface area is 3140.0
```
   
<br />
### Programming error   
// 프로그래밍 에러   
   
// 설계 미숙, 결함 또는 문법 오류로 프로그램이 의도한 대로 결과를 생성하지 못하는 문제   
// - 구문 오류 (syntax error) : 문법 체계에서 적합하지 않는 명령문 입력 시 발생   
// - 실행 오류 (runtime error) : 논리적으로 실행 불가능한 명령문 작성 시 발생   
// - 의미 오류 (semantic error) : 의미적으로 잘못 해석되는 명령문 작성 시 발생   
- It is a problem in which the program fails to produce the results as intended due to design inexperience, defects, or grammatical errors   
  - Syntax error : Occurs when entering an unsuitable command statement in the grammatical system   
  - Runtime error : Occurs when writing a logically unworkable command statement   
  - Semantic error : Occurs when writing a command statement that is misinterpreted meaningfully   
   
<br />
### Data type conversion   
// 데이터 타입 변환   
   
// input 함수를 통해 정수 30을 입력하면 변수에 들어가는 변수값은 숫자가 아닌 문자 형태 30으로 변환됨 → 30을 숫자로 이용하기 위해서는 정수 30으로 다시 변환해주는 무언가가 필요함   
- When the integer 30 is entered through the input function, the variable value that enters the variable is converted into a string type form 30 rather than a number → To use 30 as a number, something that converts it back to the integer 30 is necessary   
   
// 데이터 타입을 다른 타입으로 전환해주는 함수   
// - 문자열 타입으로 변환 : str 함수   
// - 정수 타입으로 변환 : int 함수   
// - 소수 타입으로 변환 : float 함수   
- Functions that convert data types to other types   
  - Converting to string type: str function   
  - Converting to integer type : int function   
  - Converting to float type: float function   
   
<br />
### Extensions of print function   
// print 함수의 확장   
   
// 여러 개의 데이터를 단일 함수로 출력 가능   
// - 콤마 ( , ) 로 파라미터를 구분하여 입력   
// - 데이터 사이에 공백 (기본값) 이 자동으로 추가됨   
// - sep 옵션을 변경하여 공백 변경 가능   
- Multiple data can be output as a single function   
  - Enter parameters separated by the comma ( , )   
  - Space (default) is automatically added between data   
  - Change the sep option to change the space   
   
```python
print("The volume of the cone is ", vol, sep="")
```
   
<br />
### Selection structure   
// 선택 구조   
   
// 특정 영역 내의 명령문에 대한 실행 여부를 프로그램 실행 과정 중에 결정하는 구조   
// - 실행 여부는 조건에 따라 결정됨   
- A structure that determines whether to execute a command statement within a specific area during the program execution process   
  - Whether to run depends on the conditions   
   
#### Syntax format of the selection structure   
// 선택 구조의 구문 형식   
   
// 들여쓰기는 코드 블록을 표현   
// 특정 동작을 수행하는 한 라인 이상의 명령문의 집합   
// 스페이스 4칸 권고 (PEP-8)   
- Indent represents a block of code   
- A set of command statements on one or more lines that perform a particular action   
- 4 spaces are recommended (PEP 8)   
   
```python
# if 불리언식 :
#     명령문 1
#     명령문 2
if Bulian expression :
    Command statement 1
    Command statement 2
```
   
#### Bulian expression   
// 불리언식   
   
// 비교 연산자를 사용하여 결과가 불리언 타입으로 생성되는 표현식   
- Expression in which the result is created in a boolean type using the comparison operator   
   
|// 연산자<br />Operator|// 수학적 표현<br />Mathematical expressions|// 의미<br />Meaning|
|:---:|:---:|:---|
|＜|＜|// 작다<br />- Small|
|＜=|＜≤|// 작거나 같다<br />- Small or Equal|
|＞|＞|// 크다<br />- Large|
|＞=|≥|// 크거나 같다<br />- Large or Equal|
|==|=|// 같다<br />- Equal|
|!=|≠|// 같지 않다<br />- Not Equal|
   
#### Boolean type   
// 불리언 타입   
   
// 논리적인 참 (True) 과 거짓 (False) 의 값만 표현할 수 있는 데이터 타입   
// - True 또는 False 예약어를 사용하여 표현   
// - 비교 연산자를 사용한 표현식의 결과로 생성   
- Type of data that can represent only logical true and false values   
  - Express using True or False reservation words   
  - Create as a result of an expression with a comparison operator   
   
- Example   
   
```python
3 < 6
```
   
- Result   
   
```
True
```
   
- Example   
   
```python
rad = 10
rad == 10
```
   
- Result   
   
```
True
```
   
- Example   
   
```python
right_on = 3 > 6
print(right_on)
```
   
- Result   
   
```
False
```
   
- Example   
   
```python
suf = 10
vol = 20
isStop = suf == vol
print(isStop)
```
   
- Result   
   
```
False
```
   
<br />
### Python practice   
// 파이썬 실습   
   
// 원뿔 계산 프로그램 개선   
// - 원뿔의 부피 & 겉넓이 계산 프로그램   
// -- 부피 = 1/3πr²h   
// -- 겉넓이 = πr² + πrh   
// - 사용자로부터 반지름과 높이를 입력받고 계산   
// - 반지름이 0이나 음수가 입력된 경우 실행되지 않도록 예외처리   
- Improvement of the cone calculation program   
  - Calculation program for volume & surface area of cone   
    - Volume = 1/3πr²h   
    - Surface area = πr² + πrh   
  - Receive and calculate the radius and height from the user   
  - Handling exceptions to prevent running if a radius is zero or negative number   
   
```python
# 반지름, 높이 값 할당
# Assign radius, height value
rad = int(input("Enter a value for the radius : "))
hei = int(input("Enter a value for the height : "))

if rad > 0 :
    # 부피 출력
    # Volume Output
    vol = 1 / 3 * 3.14 * rad ** 2 * hei
    # 겉넓이 출력
    # Surface area Output
    suf = 3.14 * rad ** 2 + 3.14 * rad * hei
    print("The value of the volume is ", vol, sep="")
    print("The value of the surface area is ", suf, sep="")
```
   
- Result   
   
```
Enter a value for the radius : -4 [Enter]
Enter a value for the height : 30 [Enter]
```
   
<br />
### Logical operator   
// 논리 연산자   
   
#### Concept of Logical operator   
// 논리 연산자의 개념   
   
// 참, 거짓을 구별할 수 있는 명제를 대상으로 명제의 집합을 위해 고안한 연산자   
// 두 개의 논리값 (불리언식) 을 연산하여 참 또는 거짓을 결과로 얻는 연산자   
// - 두 개의 피연산자를 갖는 이항 연산자   
// - 'and' (논리곱), 'or' (논리합), 'not' (논리부정) 연산자 사용   
// - 왼쪽에서 오른쪽의 방향으로 결합   
- An operator designed for a set of propositions that can distinguish between true and false   
- An operator who computes two logical values (Bulian expression) to obtain true or false results   
  - Binary operator with two operands   
  - Use 'and' (conjunction), 'or' (disjunction), 'not' (negation) operators   
  - Combine from left to right   
   
#### and   
   
// 두 논리값이 모두 True 일 때 True 이고, 어느 하나라도 False 일 경우 False 반환   
- Returns True when both logical values are True, and False if either is False   
   
// 진리표   
- Truth table   
   
|b1|b2|b1 and b2|
|:---:|:---:|:---:|
|False|False|False|
|False|True|False|
|True|False|False|
   
- Example   
   
```python
temp = 20
fruit = "apple"
print(temp <= 27 and fruit =="apple")
```
   
- Result   
   
```
True
```
   
#### or   
   
// 두 논리값이 모두 False 일 때 False 이고, 어느 하나라도 True 일 경우 True 반환   
- Returns False when both logical values are False, and True if either is True   
   
// 진리표   
- Truth table   
   
|b1|b2|b1 and b2|
|:---:|:---:|:---:|
|False|False|False|
|False|True|True|
|True|False|True|
   
- Example   
   
```python
temp = 20
fruit = "apple"
print(temp >= 27 or fruit =="apple")
```
   
- Result   
   
```
True
```
   
#### not   
   
// 단항 연산자로 논리값을 반전하여 False 는 True 로, True 는 False 로 반환   
- As a unary operator, inversion of the logic value, False returns True, and True returns False   
   
// 진리표   
- Truth table   
   
|b1|not b1|
|:---:|:---:|
|False|True|
|True|False|
   
- Example   
   
```python
temp = 20
print(not temp <= 27)
```
   
- Result   
   
```
False
```
   
#### Short-circuit evaluation   
// 단락평가   
   
// 첫 번째 논리값 만으로 전체 연산 결과가 판별 가능할 때 두 번째 논리값은 확인 (평가) 하지 않는 기법   
- If the entire operation result can be determined only by the first logic value, the second logic value is a technique that does not check (evaluate)   
   
<br />
### Python practice   
// 파이썬 실습   
   
// 원뿔 계산 프로그램 개선   
// - 원뿔의 부피 & 겉넓이 계산 프로그램   
// -- 부피 = 1/3πr²h   
// -- 겉넓이 = πr² + πrh   
// - 사용자로부터 반지름과 높이를 입력받고 계산   
// - 반지름이 0이나 음수가 입력된 경우 실행되지 않도록 예외처리   
// - 높이가 0이나 음수가 입력된 경우 실행되지 않도록 예외처리   
- Improvement of the cone calculation program   
  - Calculation program for volume & surface area of cone   
    - Volume = 1/3πr²h   
    - Surface area = πr² + πrh   
  - Receive and calculate the radius and height from the user   
  - Handling exceptions to prevent running if a radius is zero or negative number   
  - Handling exceptions to prevent running if a height is zero or negative number   
   
```python
# 반지름, 높이 값 할당
# Assign radius, height value
rad = int(input("Enter a value for the radius : "))
hei = int(input("Enter a value for the height : "))

if rad > 0 and hei > 0 :
    # 부피 출력
    # Volume Output
    vol = 1 / 3 * 3.14 * rad ** 2 * hei
    # 겉넓이 출력
    # Surface area Output
    suf = 3.14 * rad ** 2 + 3.14 * rad * hei
    print("The value of the volume is ", vol, sep="")
    print("The value of the surface area is ", suf, sep="")
```
   
- Result   
   
```
Enter a value for the radius : 20 [Enter]
Enter a value for the height : -4 [Enter]
```
   
<br />
### Extensions of selection structure   
// 선택 구조의 확장   
   
#### Syntax format of the dichotomous selection structure   
// 이분 선택 구조의 구문 형식   
   
```python
# if 불리언식 :
#     명령문 1
# else :
#     명령문 2
if Bulian expression :
    Command statement 1
else :
    Command statement 2
```
   
- Example   
   
```python
# 반지름, 높이 값 할당
# Assign radius, height value
rad = int(input("Enter a value for the radius : "))
hei = int(input("Enter a value for the height : "))

if rad > 0 and hei > 0 :
    # 부피 출력
    # Volume Output
    vol = 1 / 3 * 3.14 * rad ** 2 * hei
    # 겉넓이 출력
    # Surface area Output
    suf = 3.14 * rad ** 2 + 3.14 * rad * hei
    print("The value of the volume is ", vol, sep="")
    print("The value of the surface area is ", suf, sep="")
else : 
    print("Enter both radius and height values as positive numbers")
```
   
- Result   
   
```
Enter a value for the radius : -3 [Enter]
Enter a value for the height : 30 [Enter]
Enter both radius and height values as positive numbers
```
   
#### Syntax format of the multi-selective structure   
// 다분 선택 구조의 구문 형식   
   
```python
# if 불리언식 1 :
#     명령문 1
# elif 불리언식 2 :
#     명령문 2
#     ...
# elif 불리언식 n :
#     명령문 n
# else :
#     명령문 n+1
if Bulian expression 1 :
    Command statement 1
elif Bulian expression 2 :
    Command statement 2
    ...
elif Bulian expression n :
    Command statement n
else :
    Command statement n+1
```
   
// 마지막 else 는 생략 가능   
- Last else can be omitted   
   
#### Syntax format of the nesting selection structure   
// 중첩 선택 구조의 구문 형식   
   
```python
# if out불리언식 :
#     if in불리언식 1 :
#         in명령문 1
#     else :
#         in명령문 2
# else :
#     if in불리언식 2 :
#         명령문 3
if outBulianExpression :
    if inBulianExpression 1 :
        inCommandStatement 1
    else :
        inCommandStatement 2
else :
    if inBulianExpression 2 :
        Command statement 3
```
   
<br />
### Python practice   
// 파이썬 실습   
   
// 가장 큰 수를 찾는 프로그램   
// - 세 수 A, B, C를 입력 받고 그 중 가장 큰 수를 출력하는 프로그램   
- Program for finding the largest number   
  - Program that receives three numbers A, B, and C and outputs the largest number of them   
   
```python
# A, B, C 사용자 입력
# A, B and C are entered by the user
A = int(input("Enter A : "))
B = int(input("Enter B : "))
C = int(input("Enter C : "))

# A, B, C 중 가장 큰 수 출력 - 내장함수 max 활용
# Output the largest number among A, B and C - Utilize built-in function max
abc = max(A, B, C)
print("abc는", abc)

# A, B, C 중 가장 큰 수 출력 - 사용자 정의 함수 활용
# Output the largest number among A, B and C - Utilize User-defined function
if A > B :
    if A > C :
        print("The largest number is A :", A)
    else :
        print("The largest number is C :", C)
else :
    if B > C :
        print("The largest number is B :", B)
    else :
        print("The largest number is C :", C)
```
   
- Result   
   
```
Enter A : -3 [Enter]
Enter B : -2 [Enter]
Enter C : -1 [Enter]
abc는 -1
The largest number is C : -1
```
   
<br />
### Iteration structure   
// 반복 구조   
   
// 특정 영역의 명령문을 여러 번 재실행하는 구조   
// - 반복 횟수를 조건에 따라 결정함   
- Structures that re-execute command statements in a particular area multiple times   
  - Determines the number of iterations based on conditions   
   
<br />
### Definition of iteration structure   
// 반복 구조의 정의   
   
#### Concept of iteration structure   
// 반복 구조의 개념   
   
// 특정 영역의 명령문을 여러 번 실행하는 구조   
// - 반복 횟수를 조건에 따라 결정   
// - loop, iterate, repeat 용어가 혼용   
- A structure that executes a command statement in a particular area multiple times   
  - Determines the number of iterations based on conditions   
  - Loop, iterate, repeat terms are used interchangeably   
   
#### Syntax format of the iteration structure   
// 반복 구조의 구문 형식   
   
// 조건 제어 반복   
- Condition control iteration   
   
```python
# while 반복-계속-조건 : 
#     코드 블록
while iteration-continuation-condition : 
    code block
```
   
// 계수 제어 반복   
- Coefficient control iteration   
   
```python
# for 계수-제어-변수 in 시퀀스 :
#     코드 블록
for coefficient-control-variable in 시퀀스 :
    code block
```
   
#### Fear of the iteration structure   
// 반복 구조의 공포   
   
// 반복 구조를 사용할 때에는 종료가 되는지 꼭 판단해야 함   
// 종료를 해 줄 수 있는 감시자 (sentinel) 가 꼭 있어야 함   
- When using a repeating structure, you must determine whether it is terminated   
- There must be a sentinel to shut down   
   
#### Strategies for iteration structure design   
// 반복 구조 설계 전략   
   
// 단계 1 : 반복되어야 하는 명령 블록을 작성   
- Step 1 : Create a command block that must be repeated   
   
// 단계 2 : 반복되어야 하는 명령문을 다음과 같이 반복 구조로 작성   
- Step 2 : Write a command statement that needs to be repeated in a repeating structure   
   
```python
# while True :
#     명령 블록
while True :
    command block
```
   
// 단계 3 : 반복-계속-조건을 작성하고 반복 구조를 제어하기 위해 반복 제어 명령문을 추가   
- Step 3 : To create an iteration-continuation-condition and control the iteration structure, add an iteration control command statement   
   
```python
# while 반복-계속-조건 :
#     명령 블록
#     반복 제어 명령문
while iteration-continuation-condition :
    command block
    iteration control command statement
```
   
<br />
### Python practice   
// 파이썬 실습   
   
// 반복 출력 프로그램   
// - '저는 파이썬을 잘 다룰 수 있습니다' 를 5번 출력하는 프로그램을 작성하시오   
- Iterative output program   
  - Write a program that prints 'I can handle Python well' five times   
   
```python
# 메시지 저장
# Save Message
msg = "I can handle Python well"

# 5번 반복 출력
# Repeated output 5 times
count = 1
while count <= 5 :
    print(msg)
    count = count + 1
```
   
- Result   
   
```
I can handle Python well
I can handle Python well
I can handle Python well
I can handle Python well
I can handle Python well
```
   
// n까지 합 계산 프로그램   
// - 1부터 사용자가 입력한 값 n까지 합을 구하는 프로그램을 작성하시오   
- Program that computes a sum up to n   
  - Write a program to find the sum from 1 to the value n entered by the user   
   
// 반복 구조 설계 전략 적용   
- Apply the strategies for iteration structure design   
   
// 단계 1 : 반복되어야 하는 명령 블록을 작성   
- Step 1 : Create a command block that must be repeated   
   
```python
sum = sum + i
```
   
// 단계 2 : 반복되어야 하는 명령문을 다음과 같이 반복 구조로 작성   
- Step 2 : Write a command statement that needs to be repeated in a repeating structure   
   
```python
while True :
    sum = sum +i
```
   
// 단계 3 : 반복-계속-조건을 작성하고 반복 구조를 제어하기 위해 반복 제어 명령문을 추가   
- Step 3 : To create an iteration-continuation-condition and control the iteration structure, add an iteration control command statement   
   
```python
sum = 0
i = 1
last = int(input("Which number should add? : "))
while i <= last :
    sum = sum + i
    i = i + 1
print(sum)
```
   
- Result   
   
```
Which number should add? : 2 [Enter]
3
```
   
// 구구단 출력 프로그램   
// - 사용자가 입력한 단의 구구단 출력   
- Program that outputs a multiplication table   
  - Outputs the multiplication tables of the steps input by the user   
   
```python
base = int(input("Please enter the step you want to print : "))
i = 1
while i <= 9 :
    print(base, "X", i, "=", base * i)
    i = i + 1
```
   
- Result   
   
```
Please enter the step you want to print : 2 [Enter]
2 X 1 = 2
2 X 2 = 4
2 X 3 = 6
2 X 4 = 8
2 X 5 = 10
2 X 6 = 12
2 X 7 = 14
2 X 8 = 16
2 X 9 = 18
```
   
<br />
### List   
// 리스트   
   
#### Concept of list   
// 리스트의 개념   
   
// 순서화된 값의 집합체를 저장할 수 있는 데이터 타입   
// - 단일 식별자로 연속된 저장 공간 접근 수단 제공   
// - 개별 원소의 값을 수정, 추가, 삭제 가능   
// - 원소 (element) 의 나열을 저장할 수 있는 시퀀스 타입 중 하나   
// -- 리스트, 세트, 투플, 딕셔너리 등   
- The type of data that can store a collection of ordered values   
  - As a single identifier, it provides a means of accessing continuous storage space   
  - A list can modify, add, or delete the values of individual elements   
  - It is one of the sequence types that can store a list of elements   
    - list, set, tuple, dictionary, etc.   
   
#### Composition of List   
// 리스트의 구성   
   
// 원소들의 순서를 표현   
- Representing the order of the elements   
   
#### Creating a list   
// 리스트의 생성   
   
```python
# list([원소 시퀀스])
# [원소 시퀀스]
list([Element Sequence])
[Element Sequence]
```
   
// 인용부호 `[` 와 `]` 를 사용하여 표현   
// 원소는 콤마 ( , ) 로 나열   
- Express with quotation marks `[` and `]`   
- Elements are listed in commas ( , )   
   
- Example   
   
```python
[1, 4, 14, 26, 31]
hei_list = [1, 4, 14, 26, 31]
body = [181, 78, "dark brown", "black"]
```
   
#### Index Operator   
// 인덱스 연산자   
   
// 시퀀스 타입의 원소에 접근하는 연산자   
// - 접근 연산자 `[, ]` 사용   
// - 원소에 부여된 인덱스 번호로 지칭   
- An operator approaching an element of a sequence type   
  - Using the access operator `[, ]`   
  - Refer to the index number assigned to the element   
   
- Example   
   
```python
print(hei_list[2])
hei_list[4] = 45
```
   
#### Use of coefficient control iteration   
// 계수 제어 반복의 사용   
   
// 계수-제어-변수와 시퀀스 사용   
// 반복 시 계수-제어-변수에 시퀀스의 원소 할당   
- Use coefficient-control-variable and sequence   
- Assigning elements of a sequence to a coefficient-control-variable at iteration   
   
```python
# for 계수-제어-변수 in 시퀀스 :
#     코드 블록
for coefficient-control-variable in 시퀀스 :
    code block
```
   
- Example   
   
```python
# 리스트 생성
# Create a list
hei_list = [1, 4, 14, 26, 31]

for hei in hei_list :
    print(hei)
```
   
- Result   
   
```
1
4
14
26
31
```
   
<br />
### Python practice   
// 파이썬 실습   
   
// 원뿔 계산 프로그램 개선   
// - 원뿔의 부피 & 겉넓이 계산 프로그램   
// -- 부피 = 1/3πr²h   
// -- 겉넓이 = πr² + πrh   
// - 반지름이 10이고 높이가 1, 5, 14, 26, 31인 원뿔의 부피와 겉넓이를 각각 출력하시오   
- Improvement of the cone calculation program   
  - Calculation program for volume & surface area of cone   
    - Volume = 1/3πr²h   
    - Surface area = πr² + πrh   
  - Output the volume and surface area of a cone with a radius of 10 and a height of 1, 5, 14, 26, 31 respectively   
   
```python
rad = 10
hei_list = [1, 5, 14, 26, 31]

for hei in hei_list :
    # 부피&겉넓이 계산
    # Calculation of Volume & Surface area
    vol = 1/3 * 3.14 * rad ** 2 * hei
    surf = 3.14 * rad ** 2 + 3.14 * rad * hei
    print("Radius ", rad, "Height ", hei, " Cone")
    print("The volume of the cone is " ,vol)
    print("The surface area of the cone is " ,surf)
```
   
- Result   
   
```
Radius 10 Height 1 Cone
The volume of the cone is 104.66666666666666
The surface area of the cone is 345.4
Radius 10 Height 5 Cone
The volume of the cone is 523.3333333333333
The surface area of the cone is 471.0
Radius 10 Height 14 Cone
The volume of the cone is 1465.3333333333333
The surface area of the cone is 753.6
Radius 10 Height 26 Cone
The volume of the cone is 2721.333333333333
The surface area of the cone is 1130.4
Radius 10 Height 31 Cone
The volume of the cone is 3244.6666666666665
The surface area of the cone is 1287.4
```
   
<br />
### Extensions of iteration structure   
// 반복 구조의 확장   
   
#### Automate list create   
// 리스트 생성 자동화   
   
// 리스트 내 원소에 규칙성이 있는 경우 생성 자동화를 위해 함수 사용 가능   
- If the elements in the list have regularity, a function is available for automation of creation   
   
```python
range(a, b, k)
```
   
// a 부터 b 보다 작은 값까지 k씩 증가시켜 시퀀스 생성   
// a는 생략 가능. 생략 시 기본값 0   
// k는 생략 가능. 생략 시 기본값 1   
- From a to less than b, increase by k to create a sequence   
- a can be omitted. Default value 0 when omitted   
- k can be omitted. Default value 1 when omitted   
   
#### Using the range function   
// range 함수의 사용   
   
- Example   
   
```python
range(1, 100, 1)
```

- Result   
   
```python
[1, 2, 3, 4, 5, ..., 99]
```
   
- Example   
   
```python
rad_list = range(10, 40, 10)
```
   
- Result   
   
```python
[10, 20, 30]
```
   
<br />
### Python practice   
// 파이썬 실습   
   
// 반복 출력 프로그램 개선   
// - '저는 파이썬을 잘 다룰 수 있습니다' 를 5번 출력하는 프로그램을 작성하시오   
- Improve iterative output program   
  - Write a program that prints 'I can handle Python well' five times   
   
```python
# 메시지 저장
# Save Message
msg = "I can handle Python well"

# 5번 반복 출력
# Repeated output 5 times
for count in range(1, 6) : 
    print(msg)
```
   
- Result   
   
```
I can handle Python well
I can handle Python well
I can handle Python well
I can handle Python well
I can handle Python well
```
   
// 원뿔 계산 프로그램 개선   
// - 원뿔의 부피 & 겉넓이 계산 프로그램   
// -- 부피 = 1/3πr²h   
// -- 겉넓이 = πr² + πrh   
// - 반지름과 높이가 (10, 1), (20, 5), (30, 14) 인 원뿔의 부피와 겉넓이를 각각 출력하시오   
- Improvement of the cone calculation program   
  - Calculation program for volume & surface area of cone   
    - Volume = 1/3πr²h   
    - Surface area = πr² + πrh   
  - Output the volume and surface area of a cone whose radius and height are (10, 1), (20, 5), (30, 14), respectively   
   
```python
rad_list = range(10, 31, 10)
hei_list = [1, 5, 14]

for rad, hei in zip(rad_list, hei_list) :
    # 부피&겉넓이 계산
    # Calculation of Volume & Surface area
    vol = 1/3 * 3.14 * rad ** 2 * hei
    surf = 3.14 * rad ** 2 + 3.14 * rad * hei
    print("Radius ", rad, "Height ", hei, " Cone")
    print("The volume of the cone is " ,vol)
    print("The surface area of the cone is " ,surf)
```
   
- Result   
   
```
Radius 10 Height 1 Cone
The volume of the cone is 104.66666666666666
The surface area of the cone is 345.4
Radius 20 Height 5 Cone
The volume of the cone is 2093.333333333333
The surface area of the cone is 1570.0
Radius 30 Height 14 Cone
The volume of the cone is 13188.0
The surface area of the cone is 4144.8
```
   
<br />
### Overlapping iteration structure   
// 중첩 반복 구조   
   
// 반복 구조 내에 다른 반복구조를 내포하는 형식   
- A format that contains a different iteration structure within a iteration structure   
   
```python
# for 계수-제어-변수1 in 시퀀스1 :
#     for 계수-제어-변수2 in 시퀀스2 :
#         명령 블록
for coefficient-control-variable 1 in sequence 1 :
    for coefficient-control-variable 2 in sequence 2 :
        command block
```
   
#### Fear of the overlapping iteration structure   
// 중첩 반복 구조의 공포   
   
// 반복 횟수가 급격히 증가할 수 있는 중첩 구조이니 실습 금지! 최소 1분 이상 걸림   
- Don't practice! Overlapping structure that can increase the number of iterations rapidly. Take at least 1 minute   
   
```python
for i in range (1000) :
    for j in range (1000) :
        for k in range (1000) :
            i * j * k
```
   
<br />
### format function   
// format 함수   
   
// 데이터를 양식에 맞춰 형식화   
- Formalize the data according to the form   
   
```python
format("TIMES", ">10s")
```
   
// "구구단표" 는 변경 대상 데이터임   
// ">10s" 은 형식 지정자임   
- "TIMES" is the data to be changed   
- ">10s" is a type specifier   
   
// 형식 지정자   
// - `>` 는 정렬 방향   
// - `10` 은 필드 폭   
// - `s` 는 데이터 타입 (d : 정수, s : 문자열)   
- Type specifier   
  - `>` is the alignment direction   
  - `10` is field width   
  - `s` is the data type (d : integer, s : string)   
   
#### Using the format function   
// format 함수의 사용   
   
// 문자열 형식   
// - 문자 타입은 왼쪽 정렬이 기본   
- String format   
  - For string types, left alignment is the default   
   
```python
format("TIMES", ">10s")
```
   
|1|2|3|4|5|6|7|8|9|10|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
||||||T|I|M|E|S|
   
// 정수 형식   
// - 정수 타입은 오른쪽 정렬이 기본   
- Integer format   
  - For integer types, right alignment is the default   
   
```python
format(1234, "<10d")
```
   
|1|2|3|4|5|6|7|8|9|10|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|1|2|3|4|||||||
   
<br />
### Python practice   
// 파이썬 실습   
   
// 구구단 출력 프로그램 개선   
// - 구구단표 전체 출력   
- Improved program that outputs a multiplication table   
  - Full output of multiplication tables   
   
```python
print(format("TIMES",">20s"))

# 표 머리 출력
# Output table head
print("  |", end = "")
for j in range(1, 10) :
    print("  ", j, end = "")
# 새로운 행 삽입
# Insert a new row
print()
print("-----------------------------------------")

# 구구단 표 출력
# Full output of multiplication tables
for i in range(1, 10, 1) :
    print(i, "|", end="")
    for j in range(1, 10, ) :
        print(format(i * j, ">4d"), end="")
    print()
```
   
- Result   
   
```
               TIMES
  |   1   2   3   4   5   6   7   8   9
-----------------------------------------
1 |   1   2   3   4   5   6   7   8   9
2 |   2   4   6   8  10  12  14  16  18
3 |   3   6   9  12  15  18  21  24  27
4 |   4   8  12  16  20  24  28  32  36
5 |   5  10  15  20  25  30  35  40  45
6 |   6  12  18  24  30  36  42  48  54
7 |   7  14  21  28  35  42  49  56  63
8 |   8  16  24  32  40  48  56  64  72
9 |   9  18  27  36  45  54  63  72  81
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
