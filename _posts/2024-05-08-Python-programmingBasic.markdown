---
layout: post
title:  "Python: Programming Basic"
date:   2024-05-08 09:00:00 +0900
categories: [Python]
---

### Programming Basic   
// 프로그래밍 기초   
   
#### Number   
// 숫자   
   
// 정수 (integer) : 소수점이 없는 숫자   
// 실수 (floating point) : 소수점이 포함되는 숫자   
- Integer : A decimal-free number   
- Floating point : A number containing a decimal point   
   
// 정수와 실수의 표현 방법이 다르기 때문에 파이썬에서는 서로 다르게 표현   
- Since the expression methods of integers and real numbers are different, Python expresses them differently   
   
#### Character   
// 문자   
   
// 유니코드 (unicode) 기반 문자 또는 문자열   
// 인용 부호 " 또는 '를 사용하여 표현   
// 전 세계의 모든 문자들을 표현하기 위해 가변 길이의 4byte로 문자를 표현하는 코드 체계   
// 파이썬 3.0부터는 모든 문자를 유니코드로 처리   
// 문자가 하나이든 여러 개이든 파이썬에서는 모두가 문자 타입으로 처리함   
- Unicode based character or string   
- Express using quotation marks " or '   
- A code system that expresses characters in 4 bytes of variable length to represent all characters in the world   
- Starting with Python 3.0, all characters are processed in Unicode   
- Whether it's just one or more characters, Python processes everything as a character type   
   
#### Basic Operator and Expression   
// 기본 연산자와 표현식   
   
// 피연산자와 연산자를 이용한 표현식은 파이썬 인터프리터에 의해 자동 계산됨   
- Expression using operands and operators is automatically calculated by the Python interpreter   
   
|Operator|function|
|:---:|:---:|
|+|// 더하기<br />- Addition|
|-|// 빼기<br />- Subtraction|
|*|// 곱하기<br />- Multiplication|
|/|// 나누기<br />- Division|
|**|// 지수(거듭제곱)<br />- Exponent (power)|
   
#### Function   
// 함수   
   
// 특정 작업을 수행하는 코드의 집합으로 함수의 이름만으로 실행할 수 있는 단위   
// - 예시 : print 함수 : 화면에 데이터를 출력하는 작업   
- A set of codes that perform a particular task that can be executed by the name of the function alone   
  - Example : print function : Task of outputting data to the screen   
   
// 함수의 기본 구조   
- Basic structure of a function   
   
```python
print("Hello World!")
```
   
// print 는 함수명, "Hello World!" 는 입력값 (파라미터)   
- print is a function name, and "Hello World!" is an input value (parameter)   
   
#### Indent   
// 들여쓰기   
   
// 파이썬은 들여쓰기에 의존적 언어   
// - 타 프로그래밍 언어에서는 가독성 향상 목적   
// - 파이썬에서 코드의 논리적 집합인 블록을 표현   
// -- 파이썬에서는 들여쓰기를 의미없이 함부로 넣으면 안됨   
- Python is an indent-dependent language   
  - In other programming languages, the purpose is to improve readability   
  - Indent represents a block in Python, which is a logical set of codes   
    - In Python, indent is not allowed without meaning   
   
// 들여쓰기는 스페이스 4칸을 권장 (PEP 8)   
// 블록 중첩 시 추가적인 4칸 들여쓰기 삽입   
- 4 spaces are recommended for indent (PEP 8)   
- Insert additional 4 spaces indent when overlapping blocks   
   
#### Documentation   
// 문서화   
   
// 주석 (comment) 사용   
// - 가독성 증대로 개발 속도 향상, 유지보수 용이   
- Using comment   
  - Speed development and ease of maintenance due to increased readability   
   
// 주석의 종류   
// - 한 라인 주석에 `#` 을 사용   
// - 여러 라인 주석에는 `"""` 또는 `'''` 3개를 연달아 사용   
- Types of comment   
  - Use `#` for one line comment   
  - Multiple line comments use three consecutive `"""` or `'''`   
   
<br />
### Python practice   
// 파이썬 실습   
   
// 아래아한글이나 MS Word에서 복사해 붙인 코드는 에러가 발생할 수 있으니 주의 필요   
- Codes copied from Hangul or MS Word may cause errors, so care should be taken   
   
// 코드 실행 순서   
// - colab 에서 `새 노트` 선택하여 새로운 노트가 열리면 `+코드` 선택하여 코드 입력 창 열기   
// - → 코드 입력 후 `ctrl + Enter` 선택하여 코드 실행   
// - → 실행 결과가 코드 입력 창 아래에 나타남   
- Code run order   
  - Select `New Note` in colab to open a new note, select `+Code` to open a code entry window   
  - → After entering the code, select `ctrl + Enter` to execute the code   
  - → Execution results appear below the code entry window   
   
// 코드 입력 후 `shift + Enter`를 선택하면 코드 실행과 동시에 코드 입력 창이 추가로 열림   
- If `shift + Enter` is selected after code entry, the code entry window opens further upon code execution   
   
// print 함수를 사용하지 않으면 에코 기능으로 실행 결과가 코드 입력 창 아래에 나타남   
- If the print function is not used, the Echo function shows the execution result under the code entry window   
   
- Example   
   
```python
3.141592
```
   
- Result   
   
```
3.141592
```
   
- Example   
   
```python
"Computer"
```
   
- Result   
   
```
Computer
```
   
- Example   
   
```python
"Hello World!"
```
   
- Result   
   
```
Hello World!
```
   
- Example   
   
```python
2*7
```
   
- Result   
   
```
14
```
   
- Example   
   
```python
(7 + 15) * 2
```
   
- Result   
   
```
44
```
   
- Example   
   
```python
2 ** 10 * 5
```
   
- Result   
   
```
5120
```
   
- Example   
   
```python
"Computer" + "science"
```
   
- Result   
   
```
Computerscience
```
   
- Example   
   
```python
"Computer" * 2
```
   
- Result   
   
```
ComputerComputer
```
   
// print 함수는 파라미터로 넘어온 값을 그대로 모니터에 출력해 줌   
- The print function outputs the value passed as a parameter to the monitor as it is   
   
- Example   
   
```python
print(2 * 7)
```
   
- Result   
   
```
14
```
   
- Example   
   
```python
print("Hello World!")
print("Python is Fun")
```
   
- Result   
   
```
Hello World!
Python is Fun
```
   
// 주석 작성 시 예시   
- Example when comment   
   
```python
# 학점 계산
# Calculation of credits
print((4.5 * 2 + 4.0 * 3) / 2)
```
   
- Result   
   
```
10.5
```
   
<br />
### Save data   
// 데이터 저장   
   
// 예시   
// - 원뿔의 부피 & 겉넓이 계산 프로그램   
// -- 부피 = 1/3πr²h   
// -- 겉넓이 = πr² + πrh   
- Example   
  - Calculation program for volume & surface area of cone   
    - Volume = 1/3πr²h   
    - Surface area = πr² + πrh   
   
```python
# 반지름, 높이 값 할당
# Assign radius, height value
rad = 20
hei = 30
# 부피 출력
# Volume Output
# print(1 / 3 * 3.14 * 20 ** 2 * hei)
print(1 / 3 * 3.14 * rad * rad * hei)
# 겉넓이 출력
# Surface area Output
# print(3.14 * 20 ** 2 + 3.14 * 20 * 30)
print(3.14 * rad * rad + 3.14 * rad * hei)
```
   
#### Variable   
// 변수   
   
// 명령형 패러다임 언어의 특징   
// - 처리할 데이터와 처리된 결과를 임시적 저장   
// - 변수의 값을 변경하는 할당 연산자 (=) 를 이용   
- Characteristics of imperative paradigm language   
  - Temporarily store data to be processed and results processed   
  - Use the assignment operator (=) to change the value of the variable   
   
// 예시   
// - `rad = 20`   
// -- 오른쪽에 있는 값 (20) 을 왼쪽 (red) 에 집어 넣어라는 의미   
// -- `rad` : lvalue (지속되는 대상)   
// -- `20` : rvalue (임시적인 대상)   
- Example   
  - `rad = 20`   
    - It means to put the value (20) on the right into the left (red)   
    - `rad` : lvalue (a lasting object)   
    - `20` : rvalue (a temporary object)   
   
#### Allocation of values   
// 값의 할당   
   
// 프로그램이 실행되는 과정에서 처리되는 값이 어떤 행위 (입력, 연산 등) 에 따라 그 값이 변할 수 있는 메모리 내의 저장 공간 지정됨   
// 식별자, 저장 공간, 값으로 구성됨   
- A storage space in the memory whose value can change according to a certain action (input, operation, etc.) is designated in the process of executing a program   
- It consists of identifiers, storage space, and values   
   
#### Identifier   
// 식별자   
   
// 프로그램 내부에 정의된 객체 (변수, 함수 등) 의 이름   
// - 고유하게 만들어져야 하는 저장 공간의 이름   
// - 문자, 숫자, 밑줄로 구성   
// - 문자 또는 밑줄로만 시작 가능   
// - 예약어와 동일할 수 없음   
// - 길이 제한이 없음   
- The name of the object (variables, functions, etc.) defined inside the program   
  - The name of the storage space that must be uniquely created   
  - Consists of characters, numbers, and underscores   
  - Can only begin with character or underscore   
  - Cannot be the same as the reserved word   
  - No length limit   
   
#### Reserved word   
// 예약어   
   
// 파이썬 인터프리터에 의해 이미 문법적인 용도로 사용되어 식별자로 사용이 불가능한 단어   
- Words that have already been used for grammatical purposes by the Python interpreter and cannot be used as identifiers   
   
```python
False    await    else    import    pass    None
break    except    in    True    class    finally
is    return    and    continue    for    lambda
try    as    def    global    not    with
async    elif    if    yield    raise    or
```
   
<br />
### Python practice   
// 파이썬 실습   
   
- Example   
   
```python
print(1 / 3 * 3.14 * 20 ** 2 * 30 )
print(3.14 * 20 ** 2 + 3.14 * 20 * 30)
```
   
- Result   
   
```
12559.999999999998
3140.0
```
   
- Example   
   
```python
# 반지름, 높이 값 할당
# Assign radius, height value
rad = 20
hei = 30
# 부피 출력
# Volume Output
print(1 / 3 * 3.14 * rad ** 2 * hei )
# 겉넓이 출력
# Surface area Output
print(3.14 * rad ** 2 + 3.14 * rad * hei)
```
   
- Result   
   
```
12559.999999999998
3140.0
```
   
<br />
### Arithmetic Operator   
// 산술 연산자   
   
// 산술 연산자의 정의   
// - 피연산자 (operand) 에 대해 지정된 산술 연산을 지시하는 기호   
// -- 단항 연산자 (unary operator)   
// -- 이항 연산자 (binary operator)   
- Defining an Arithmetic Operator   
  - Symbol indicating the specified arithmetic operation for an operand   
    - Unary Operator   
    - Binary Operator   
   
// 예시   
// - `3.14 * rea` 에서 3.14 와 rad 는 피연산자, * 는 연산자임   
- Example   
  - In `3.14 * rea`, 3.14 and rad are operands, and * is operator   
   
#### Special Arithmetic Operator   
// 특수 산술 연산자   
   
// 프로그래밍 언어에서만 사용되는 연산 또는 부호   
// - 정수 나눗셈 연산자 ( // ) : 결과를 정수로만 표기   
// - 모듈로 연산자 ( % ) : 나머지 값만 가져옴   
- Operations or signs used only in programming languages   
  - Integer division operator ( // ) : Write the result only as an integer   
  - Modulo operator ( % ) : Get only the remaining values   
   
#### Operator Precedence   
// 연산자 우선순위   
   
// 표현식에 사용된 여러 연산자의 연산 순서를 결정   
- Determine the order of operations of multiple operators used in the expression   
   
// ① 괄호 내부의 수식   
// ② 재수 (거듭제곱 **) 연산자   
// ③ 곱셈, 실수 나눗셈, 정수 나눗셈, 나머지 연산자 : 왼쪽에서 오른쪽 순서로 적용   
// ④ 덧셈, 뺄셈 연산자 : 왼쪽에서 오른쪽 순서로 적용   
// ⑤ 할당 연산자   
① An expression in parentheses   
② Power ( ** ) operator   
③ Multiplication, real division, integer division, remaining operators : Apply from left to right   
④ Addition, subtraction operators : Apply from left to right   
⑤ Allocation operator   
   
<br />
### Python built-in function   
// 파이썬 내장 함수   
   
// 항상 사용되는 함수들을 파이썬 인터프리터에서 기본적으로 내장해놓고 제공   
// - Python 인터프리터는 항상 사용되는 내장된 함수 세트를 제공합니다   
- The Python interpreter provides a built-in set of functions that are always used   
  - Python interpreters provide a set of built-in functions that are always used   
   
// 파이썬 인터프리터에서 기본적으로 지원하는 함수   
// - 별도의 모듈이나 패키지 없이 사용 가능   
- Functions supported by Python interpreter by default   
  - Can be used without separate modules or packages   
   
#### Typical built-in functions   
// 대표적인 내장함수   
   
```python
max(2, 3, 4)
min(2, 3, 4)
round(3.141592)
abs(-3)
pow(2, 3)
```
   
<br />
### Python practice   
// 파이썬 실습   
   
- Example   
   
```python
5 / 2
```
   
- Result   
   
```
2.5
```
   
- Example   
   
```python
# 정수 나눗셈 연산자
# Integer division operator
5 // 2
```
   
- Result   
   
```
2
```
   
- Example   
   
```python
25 % 7
```
   
- Result   
   
```
4
```
   
- Example   
   
```python
8.4 % 0.9
```
   
- Result   
   
```
0.30000000000000016
```
   
- Example   
   
```python
number = 10
number % 2
```
   
- Result   
   
```
0
```
   
- Example   
   
```python
number = 9
number % 2
```
   
- Result   
   
```
1
```
   
- Example   
   
```python
max(2, 3, 4)
```
   
- Result   
   
```
4
```
   
- Example   
   
```python
min(2, 3, 4)
```
   
- Result   
   
```
2
```
   
- Example   
   
```python
round(3.14)
```
   
- Result   
   
```
3
```
   
- Example   
   
```python
abs(-3)
```
   
- Result   
   
```
3
```
   
- Example   
   
```python
pow(2, 3)
```
   
- Result   
   
```
8
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
