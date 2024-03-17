---
layout: post
title:  "JScript: Term"
date:   2024-03-13 09:00:00 +0900
categories: [JScript]
---

### constructor   
// 구성자   
   
// 다음 2가지의 특별한 기능을 가진 JScript 함수임   
// - JScript 함수는 new 연산자에 의해 호출됨   
// - JScript 함수는 this 키워드를 통해 새로 작성된 개체의 주소를 전달함   
// 새 개체를 초기화할 때 구성자를 사용   
- It is a JScript function with two special functions   
  - JScript function called by new operator   
  - The JScript function carries the address of a newly created object through this keyword   
- Use the Configurator when initializing a new object   
   
<br />
### intrinsic object   
// 내부 개체   
   
// 표준 JScript 언어의 일부인 개체로, 모든 스크립트에서 사용할 수 있음   
// JScript 내부 개체에는 Array, Boolean, Data, Function, Global, Math, Number, Object, RegExp, Regular Expression, String이 있음   
- Objects that are part of the standard JScript language, available for all scripts   
- JScript intrinsic object types include Array, Boolean, Data, Function, Global, Math, Number, Object, RegExp, Regular Expression, String   
   
<br />
### wrapper   
// 래퍼   
   
// 일부 다른 데이터 형식에 개체 스타일 인터페이스를 제공하기 위해 만든 개체   
// 래퍼 개체에는 Number 개체와 Boolean 개체가 있음   
- Objects created to provide object style interfaces to some other data formats   
- Wrapper object types include Number and Boolean objects   
   
<br />
### local time   
// 로컬 시간   
   
// 스크립트를 실행하는 클라이언트나 서버의 시스템 시간   
- The system time of the client or server running the script   
   
<br />
### locale   
// 로케일   
   
// 제공되는 언어와 국가/지역에 해당하는 일단의 정보   
// 로케일은 사전에 정의되는 프로그래밍 용어의 언어와 로케일 특정의 설정에 영향을 미침   
- A group of information that corresponds to the language and country/region provided   
- Locale influences the language of predefined programming terms and the locale-specific settings   
   
// 로케일 정보가 중요한 두가지 상황   
// - 로드 로케일은 키워드와 같은 용어의 언어에 영향을 미쳐 소수점과 목록 구분 기호, 날짜 형식 및 문자 정렬 순서 등의 로케일 특정의 설정을 정의함   
// - 시스템 로케일은 로케일 인식 기능을 작동시키는 방식에 영향을 미침. 예를들어, 숫자를 표시하거나 문자열을 날짜로 변환하는 경우임. 운영체제에서 제공하는 제어판 유틸리티를 사용하여 시스템 로케일을 설정함   
- Two situations where locale information is important   
  - Load locale affects the language of terms such as keywords to define locale-specific settings such as decimal points, list delimiter, date format, and character sorting order   
  - System locale affects how locale recognition functions work. For example, displaying numbers or converting a string to a date. Use the control panel utility provided by the operating system to set up the system locale   
   
<br />
### run-time error   
// 런타임 오류   
   
// 코드 실행 중 발생하는 오류임   
// 프로그램의 문이 잘못된 연산을 시도할 때 발생함   
- This is an error that occurs during code execution   
- Runtime error occurs when a statement in a program attempts an incorrect operation   
   
<br />
### string expression   
// 문자식   
   
// 일련의 연속적인 문자열을 평가하는 식   
// 문자식의 요소에는 문자열, 문자열 리터럴, String 개체 또는 문자열 변수를 반환하는 함수를 사용할 수 있음   
- An expression that evaluates a series of consecutive strings   
- An element of a character expression can use a function that returns a string, a string literal, a string object, or a string variable   
   
<br />
### string comparison   
// 문자열 비교   
   
// 2개의 문자열을 비교함   
// 비교를 수행하는 함수에 지정하지 않으면 모든 문자열 비교는 이진으로 함   
// 영어의 경우 이진 비교는 대/소문자를 구분하지만 텍스트 비교는 대/소문자를 구분하지 않음   
- Compare two strings   
- All string comparisons are binary unless you specify a function that performs a comparison   
- For English, binary comparisons are case sensitive, but text comparisons are not case sensitive   
   
<br />
### character code   
// 문자 코드   
   
// ASCII 문자 집합과 같이 특정 문자 집합을 나타내는 일련의 숫자   
- A series of numbers representing a particular set of characters, such as an ASCII character set   
   
<br />
### scope   
// 범위   
   
// 변수, 프로시저, 또는 개체의 가시성을 정의함   
// 함수에서 선언된 변수들은 해당 함수 내에서만 볼 수 있고 호출과 호출 사이에는 값들을 잃음   
- Define the visibility of a variable, procedure, or object   
- Variables that are declared in a function are visible only within that function and lose values between calls   
   
<br />
### variable   
// 변수   
   
// 이름으로 값을 저장하고 조정하는 데 사용하는 위치   
// JScript는 형식 제한이 적어서 스크립트 전체를 통해 변수 하나에 여러 종류의 데이터 형식을 사용할 수 있음   
- Where to store and adjust values by name   
- JScript has fewer format restrictions, allowing multiple types of data formats to be used for one variable throughout the script   
   
<br />
### compound statement   
// 복합문   
   
// 중괄호 ({}) 로 묶이는 일련의 문   
// 문 하나를 써서 여러 작업을 수행해야 할 때 사용할 수 있음   
- A series of statements bound by brace ({})   
- Can be used when you need to do multiple things with one statement   
   
<br />
### Boolean expression   
// 부울식   
   
// true 또는 false로 평가되는 식   
- Expression rated as true or false   
   
// 부울식이 아닌 식은 필요하면 다음 규칙에 따라 부울값으로 변환됨   
// - 모든 개체는 true로 간주함   
// - 문자열은 비어있는 경우에만 false로 간주함   
// - null 및 undefined는 false로 간주함   
// 숫자가 있거나 0인 경우에는 false로 간주함   
- Non-boolecular expressions are converted to Boolean values, if necessary, according to the following rules   
  - All objects are considered true   
  - String is considered false only when empty   
  - null and undefined are considered false   
- If there is a number or zero, it is considered false   
   
<br />
### comparison operator   
// 비교연산자   
   
// 둘 이상의 값이나 식 사이의 관계를 나타내는 문자나 기호   
// 비교연산자에는 보다 작다(<), 작거나 같다(<=), 보다 크다(>), 크거나 같다(>=), 같지 않다(!=), 같다(==)가 있음   
- a character or symbol that represents a relationship between two or more values or expressions   
- Comparison operators have smaller (<), smaller or equal (<=), larger (>), larger or equal (>=), not equal (!==), and equal (==)   
   
<br />
### Bitwise comparison   
// 비트 비교   
   
// 두 수식에서 같은 위치에 있는 비트를 비트별로 비교함   
- Bits in the same position are compared bit by bit in both equations   
   
<br />
### user-defined object   
// 사용자 정의 개체   
   
// 원본 코드에서 사용자가 만드는 개체   
- Object created by the user in the source code   
   
<br />
### property   
// 속성   
   
// 이름이 정해진 개체 특성   
// 속성은 크기, 색, 화면위치, 사용 또는 사용안함과 같은 개체의 상태 등 개체의 특성을 정의함   
- Named Object Properties   
- Attributes define an object's characteristics, such as size, color, screen location, and the state of the object, such as enabled or disabled   
   
<br />
### numeric expression   
// 수식   
   
// 숫자로 평가될 수 있는 식   
// 식의 요소에는 숫자를 산출하는 키워드, 변수, 리터럴, 연산자의 조합이 포함됨   
// 경우에 따라 문자열도 가능하면 숫자로 변환됨   
- an expression that can be evaluated in numbers   
- Elements of an expression include a combination of keywords, variables, literals, and operators that produce numbers   
- In some cases, strings are also converted to numbers if possible   
   
<br />
### expression   
// 식   
   
// 문자열, 숫자, 또는 개체를 만드는 키워드, 연산자, 변수, 리터럴의 조합   
// 계산을 하거나, 문자를 조정하거나, 함수를 호출하거나, 데이터를 테스트함   
- A combination of keywords, operators, variables, and literals that create a string, number, or object   
- Calculate, adjust characters, call functions, or test data   
   
<br />
### primitive   
// 원시   
   
// JScript 언어의 일부이며, 값에 따라 조정되는 데이터 형식   
// JScript에서 원시로 간주하는 데이터 형식에는 Number, Boolean, String, Function이 있음   
// 개체와 배열은 원시 데이터 형식이 아님   
- Data type that is part of the JScript language and is adjusted according to the value   
- Data formats considered primitive by JScript include Number, Boolean, String, and Function   
- Objects and arrays are not in primitive data format   
   
<br />
### Automation object   
// 자동화 개체   
   
// 자동화 인터페이스를 통해 다른 응용 프로그램이나 프로그래밍 도구에 노출되는 개체   
- Objects exposed to other applications or programming tools via the automation interface   
   
<br />
### comment   
// 주석   
   
// 코드 사용법을 설명하기 위해 프로그래머가 코드에 추가하는 텍스트   
// JScript에서 주석줄은 보통 '//'로 시작함   
// 여러 줄로 된 주석문을 만들려면 ' /* '와 ' */ ' 구분 기호를 사용함   
- Text that the programmer adds to the code to explain how to use it   
- Comment line in JScript usually begins with '//'   
- Use ' /*' and ' */' delimiter to create multi-line comments   
   
<br />
### class   
// 클래스   
   
// 개체의 형식을 정의   
// 런타임 시 개체의 인스턴스를 만드는 템플릿 역할을 함   
// 클래스는 개체의 속성과 그 개체의 동작을 제어하는 데 사용하는 메서드를 정의함   
- Define the type of object   
- Acting as a template for creating instances of objects at runtime   
- Classes define the properties of an object and the methods used to control its behavior   
   
<br />
### UTC (Universal Coordinated Time)   
// 협정 세계 표준시   
   
// WTS(세계 시간 표준)이 설정한 시간   
// GMT(그리니치 표준시)라고도 함   
- Time set by WTC (World Time Standard)   
- Also known as GMT (Greenwich Standard Time)   
   
<br />
### ASCII Character set   
// ASCII 문자 집합   
   
// ASCII(정보 교환용 미국 표준 코드)로 표준 영문 키보드에 있는 문자와 기호를 나타내는 데 사용하는 7비트 문자 집합   
// ASCII 문자 집합은 ANSI 문자 집합의 앞 부분에 나오는 128자(0 ~ 127)와 같음   
- A set of seven-bit characters used to represent characters and symbols on a standard English keyboard with ASCII (American Standard Code for Information Exchange)   
- ASCII character set is equal to 128 characters (0 ~ 127) in front of the ANSI character set   
   
<br />
### Undefined   
// 정의되지 않음   
   
// 변수를 만든 후 변수에 값을 지정하기 전에 주어진 특별한 값   
- A special value given after creating a variable before specifying a value in the variable   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
