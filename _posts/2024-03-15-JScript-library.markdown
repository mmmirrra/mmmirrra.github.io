---
layout: post
title:  "JScript: Library"
date:   2024-03-15 09:00:00 +0900
categories: [JScript]
---

### Features applicable to ECMA   
// ECMA에 해당되는 기능   
   
|Category|Functions, keywords|
|:---|:---|
|// 배열 처리<br />- Array processing|Array, join, lengch, reverse, sort|
|// 지정<br />- Specifying|=, OP=|
|// 부울<br />- Boolean|Boolean|
|// 주석<br />- Comment|/* ... */ or //|
|// 상수 / 리터럴<br />- Constant / Literary|NaN, null, true, false, Infinity, undefined|
|// 흐름 제어<br />- Flow control|break, continue, for, for...in, if...else, return, while|
|// 날짜와 시간<br />- Date and time|Date, <br />getDate, getDay, getFullYear, getHours, <br />getMilliseconds, getMinutes, getMonth, <br />getSeconds, getTime, <br />getTimezoneOffset,<br />getYear, <br />getUTCDate, getUTCDay, getUTCFullYear, <br />getUTCHours, getUTCMilliseconds, <br />getUTCMinutes, getUTCMonth, <br />getUTCseconds, <br />setDate, setFullYear, setHours, <br />setMilliseconds, setMinutes, setMonth, <br />setSeconds, <br />setTime, setYear, <br />setUTCDate, setUTCFullYear, setUTCHours, <br />setUTCMilliseconds, setUTCMinutes, <br />setUTCMonth, setUTCSeconds, <br />toGMTString, <br />toLocaleString, toUTCString, parse, UTC|
|// 선언<br />- Declaration|function, new, this, var, with|
|// 함수 작성<br />- Creating a Function|Function, arguments, length|
|// 전역 메서드<br />- Local Method|Global, escape, unescape, eval, <br />isFinite, <br />isNaN, <br />parseInt, parseFloat|
|// 연산<br />- Operation|Math, <br />abs, acos, asin, atan, atan2, <br />ceil, cos, <br />exp, floor, log, max, min, <br />pow, random, round, <br />sin, sqrt, tan, <br />E, <br />LN2, LN10, LOG2E, LOG10E, <br />PI, SQRT1_2, SQRT2|
|// 숫자<br />- Number|Number, <br />MAX_VALUE, MIN_VALUE, <br />NaN, <br />NEGATIVE_INFINITY, POSITIVE_INFINITY|
|// 개체 작성<br />- Creating Objects|Object, <br />new, <br />constructor, prototype, <br />toString, <br />valueOf|
|// 연산자<br />- Operator|+, -, %, *, /, <br />-, ==, !=, <br /><, <=, >, >=, <br />&&, \|\|, !, &, \|, ~, ∧, <br />＜＜＜, ＞＞, ＞＞＞, <br />? : , <br />',', <br />delete, <br />typeof, void, <br />--, ++|
|// 개체<br />- Object|Arrya, Boolean, Date, Function, Global, <br />Math, Number, Object, String|
|// 문자열<br />- String|String, charAt, charCodeAt, fromCharCode, <br />indexOf, lastIndexOf, <br />split, <br />toLowerCase, toUpperCase, <br />length|
   
<br />
### Features not applicable to ECMA   
// ECMA에 해당되지 않는 기능   
   
|Category|Functions, keywords|
|:---|:---|
|// 배열 처리<br />- Array processing|concat, <br />slice, <br />VBArray, <br />dimensions, <br />getItem, <br />lbound, <br />toArray, <br />ubound|
|// 조건부 컴파일<br />- Conditional Compilation|@cc_on, @if, @set,<br />// 조건부 컴파일 변수<br />- Conditional Compilation Variables|
|// 흐름 제어<br />- Flow control|do...while, Labeled, switch|
|// 날짜와 시간<br />- Date and time|getVarDate|
|// 열거<br />- Enumeration|Enumerator, atEnd, item, moveFirst, moveNext|
|// 오류 처리<br />- Error handling|Error, description, number, throw, try...catch|
|// 함수 작성<br />- Creating a Function|caller|
|// 연산자<br />- Operator|===, !==|
|// 개체<br />- Object|Enumerator, <br />RegExp, Regular Expression, <br />VBArray, <br />ActiveXObject, getObject|
|// 정규식과 패턴 일치<br />- Match Regular Expressions and Patterns|RegExp, index, input, lastIndex, <br />$1...$9, source, compile, exec, text,<br />// 정규식 구문<br />- Regular Expression Syntax|
|// 스크립팅 엔진 확인<br />- Verifying Scripting Engine|ScriptEngine, <br />ScriptEngineBuildVersion, <br />ScriptEngineMajorVersion, <br />ScriptEngineMinorVersion|
|// 문자열<br />- String|concat, slice, match, <br />replace, search, anchor, <br />big, blink, bold, fixed, <br />fontcolor, fontsize, italics, <br />link, small, strike, sub, sup|
   
<br />
### Function   
// 함수   
   
|Language element|Description|
|:---|:---|
|GetObject|// 파일에서 자동화 개체에 대한 참조를 반환<br />- Returns a reference to an automation object from a file|
|ScriptEngine|// 사용중인 스크립팅 언어를 나타내는 문자열을 반환<br />- Returns a string representing the scripting language in use|
|ScriptEngineBuildVersion|// 사용중인 스크립팅 엔진의 작성 버전 번호를 반환<br />- Returns the creation version number of the scripting engine in use|
|ScriptEngineMajorVersion|// 사용중인 스크립팅 엔진의 주 버전 번호를 반환<br />- Returns the primary version number of the scripting engine in use|
|ScriptEngineMinorVersion|// 사용중인 스크립팅 엔진의 보조 버전 번호를 반환<br />- Returns the secondary version number of the scripting engine in use |
   
<br />
### Method   
// 메서드   
   
|Language element|Description|
|:---|:---|
|abs|절대값을 반환|
|acos|아크코사인 값을 반환|
|anchor|개체의 특정 텍스트 양 끝에 NAME 특성을 가진 HTML앵커를 넣음|
|asin|아크사인 값을 반환|
|atan|아크탄젠트 값을 반환|
|atan2|X축과 점 (y, x) 사이의 각을 라디안값으로 반환|
|atEnd|열거자가 컬렉션의 끝에 있는지 여부를 나타내는 부울값을 반환|
|big|String 개체의 텍스트 양 끝에 `<BIG>` HTML 태그를 삽입|
|blink|String 개체의 텍스트 양 끝에 `<BLINK>` HTML 태그를 삽입|
|bold|String 개체의 텍스트 양 끝에 `<B>` HTML 태그를 삽입|
|ceil|숫자 인수보다 크거나 같은 가장 작은 정수를 반환|
|charAt|지정한 인덱스에 해당하는 문자를 반환|
|charCodeAt|지정한 문자의 유니코드 인코딩을 반환|
|compile|정규식을 내부 형식으로 컴파일|
|concat (Array)|두 배열의 조합으로 구성된 새 배열을 반환|
|concat (String)|주어진 두 문자열의 연결을 포함하는 String 개체를 반환|
|cos|코사인 값을 반환|
|dimensions|VBArray의 차원 수를 반환|
|escape|String 개체를 모든 컴퓨터에서 읽을 수 있도록 인코딩함|
|eval|JScript 코드를 검증하고 실행|
|exec|지정한 문자열에서 일치하는 부분을 검색|
|exp|자연 로그의 밑인 e의 거듭제곱 값을 반환|
|fixed|String 개체의 텍스트 양 끝에 `<TT>` HTML 태그를 삽입|
|floor|숫자 인수보다 작거나 같은 가장 큰 정수를 반환|
|fontcolor|String 개체의 텍스트 양 끝에 COLOR 특성을 가진 `<FONT>` HTML 태그를 삽입|
|fontsize|String 개체의 텍스트 양 끝에 SIZE 특성을 가진 `<FONT>` HTML 태그를 삽입|
|fromCharCode|여러 유니코드 문자 값 중에서 문자열을 반환|
|getDate|로컬 시간을 사용하여 Date 개체의 날짜 값을 반환|
|getDay|로컬 시간을 사용하여 Date 개체의 요일 값을 반환|
|getFullYear|로컬 시간을 사용하여 Date 개체의 연도 값을 반환|
|getHours|로컬 시간을 사용하여 Date 개체의 시 값을 반환|
|getItem|지정한 위치에 있는 항목을 반환|
|getMilliseconds|로컬 시간을 사용하여 Date 개체의 밀리초 값을 반환|
|getMinutes|로컬 시간을 사용하여 Date 개체의 분 값을 반환|
|getMonth|로컬 시간을 사용하여 Date 개체의 월 값을 반환|
|getSeconds|로컬 시간을 사용하여 Date 개체의 초 값을 반환|
|getTime|Date 개체의 시 값을 반환|
|getTimezoneOffset|호스트 컴퓨터와 협정 세계 표준시 (UTC) 사이의 시간차를 분으로 반환|
|getUTCDate|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 날짜 값을 반환|
|getUTCDay|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 요일 값을 반환|
|getUTCFullYear|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 연도 값을 반환|
|getUTCHours|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 시 값을 반환|
|getUTCMilleseconds|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 밀리초 값을 반환|
|getUTCMinutes|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 분 값을 반환|
|getUTCMonth|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 월 값을 반환|
|getUTCSeconds|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 초 값을 반환|
|getVarDate|Date 개체의 VT_DATE 값을 반환|
|getYear|Date 개체의 연도 값을 반환|
|indexOf|String 개체 안에서 부분 문자열이 처음 나오는 문자 위치를 반환|
|isFinite|주어진 수가 유한한지 여부를 나타내는 부울값을 반환|
|isNaN|어떤 값이 예약값이 NaN (숫자 아님) 인지 여부를 나타내는 부울값을 반환|
|italics|String 개체의 텍스트 양 끝에 `<I>` HTML 태그를 삽입|
|item|컬렉션의 현재 항목을 반환|
|join|배열 하나에 함께 연결된 모든 요소들로 구성된 String 개체를 반환|
|lastIndexOf|String 개체 안에서 부분 문자열이 마지막으로 나오는 경우를 반환|
|lbound|차원이 지정된 VBArray에서 사용하는 최저 인덱스 값을 반환|
|link|String 개체의 텍스트 양 끝에 HREF 특성을 가진 HTML 앵커를 삽입|
|log|자연 로그 값을 반환|
|match|주어진 Regular Expression 개체를 사용하여 문자열을 검색한 결과를 배열로 반환|
|max|주어진 두 수식 중 큰 값을 반환|
|min|주어진 두 수 중 작은 값을 반환|
|moveFirst|컬렉션에서 현재 항목을 첫번째 항목으로 다시 설정|
|moveNext|컬렉션에서 현재 항목을 다음 항목으로 옮김|
|parse|날짜를 포함한 문자열 구문을 분석하여 1970년 1월 1일 자정부터 해당 날짜 사이의 시간을 밀리초로 반환|
|parseFloat|문자열에서 변환된 부동 소수점 숫자를 반환|
|parseInt|문자열에서 변환된 정수를 반환|
|pow|밑을 지정한 지수만큼 거듭제곱한 값을 반환|
|random|0과 1 사이의 의사 난수 값을 반환|
|replace|정규식을 사용하여 텍스트를 바꾼 문자열의 복사본을 반환|
|reverse|요소들이 역으로 나열된 Array 개체를 반환|
|round|주어진 수식을 반올림하여 가장 가까운 정수를 반환|
|search|정규식 검색에서 첫번째로 일치하는 부분 문자열의 위치를 반환|
|setDate|로컬 시간을 사용하여 Date 개체의 날짜 값을 설정|
|setFullYear|로컬 시간을 사용하여 Date 개체의 연도 값을 설정|
|setHours|로컬 시간을 사용하여 Date 개체의 시 값을 설정|
|setMilliseconds|로컬 시간을 사용하여 Date 개체의 밀리초 값을 설정|
|setMinutes|로컬 시간을 사용하여 Date 개체의 분 값을 설정|
|setMonth|로컬 시간을 사용하여 Date 개체의 월 값을 설정|
|setSeconds|로컬 시간을 사용하여 Date 개체의 초 값을 설정|
|setTime|Date 개체의 날짜와 시간 값을 설정|
|setUTCDate|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 날짜 값을 설정|
|setUTCFullYear|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 연도 값을 설정|
|setUTCHours|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 시 값을 설정|
|setUTCMilliseconds|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 밀리초 값을 설정|
|setUTCMinutes|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 분 값을 설정|
|setUTCMonth|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 월 값을 설정|
|setUTCSeconds|협정 세계 표준시 (UTC) 를 사용하여 Date 개체의 초 값을 설정|
|setYear|Date 개체의 연도 값을 설정|
|sin|사인 값을 반환|
|slice (Array)|배열의 일정 부분을 반환|
|slice (String)|문자열의 일정 부분을 반환|
|small|String 개체의 텍스트 양 끝에 `<SMALL>` HTML태그를 삽입|
|sort|요소가 정렬된 Array 개체를 반환|
|split|문자열을 여러 개의 부분 문자열로 분리할 때 만들어지는 문자열의 배열을 반환|
|sqrt|제곱근 값을 반환|
|strike|String 개체의 텍스트 양 끝에 `<STRIKE>` HTML 태그를 삽입|
|sub|String 개체의 텍스트 양 끝에 `<SUB>` HTML 태그를 삽입|
|substr|지정한 위치에서 시작하고 지정한 길이를 갖는 부분 문자열을 반환|
|substring|String 개체 안의 지정된 위치에 있는 부분 문자열을 반환|
|sup|String 개체의 텍스트 양 끝에 `<SUP>` HTML 태그를 삽입|
|tan|탄젠트 값을 반환|
|test|검색한 문자열에 패턴이 있는지 여부를 나타내는 부울값을 반환|
|toArray|VBArray에서 변환된 JScript 표준 배열을 반환|
|toGMTString|그리니치 표준시 (GMT) 를 사용하여 문자열로 변환된 날짜를 반환|
|toLocaleString|현재 로케일을 사용하여 문자열로 변환된 날짜를 반환|
|toLowerCase|모든 영문자가 대문자로 변환된 문자열을 반환|
|toString|개체를 나타내는 문자열을 반환|
|toUpperCase|모든 영문자가 대문자로 변환된 문자열을 반환|
|toUTCString|협정 세계 표준시 (UTC) 를 사용하여 문자열로 변환된 날짜를 반환|
|ubound|차원이 지정된 VBArray에서 사용하는 최고 인덱스 값을 반환|
|unescape|escape 메서드로 인코딩한 String 개체를 디코딩|
|UTC|협정 세계 표준시 (UTC) 또는 그리니치 표준시 (GMT) 1970년 1월 1일 자정부터 주어진 날짜 사이의 시간을 밀리초로 반환|
|valueOf|지정한 개체의 원시 값을 반환|
   
<br />
### Object   
// 개체   
   
|Language element|Description|
|:---|:---|
|ActiveXObject|자동화 개체에 대한 참조를 사용하여 반환|
|Array|모든 데이터 형식의 배열을 만들 수 있도록 지원|
|Boolean|새 부울값을 만듦|
|Date|날짜와 시간을 기본으로 저장하거나 가져올 수 있음|
|Dictionary|데이터 키-항목 쌍을 저장하는 개체|
|Enumerator|컬렉션에 있는 항목들을 열거할 수 있음|
|Error|JScript 코드 실행 중 발생하는 오류에 대한 정보를 포함하는 개체|
|FileSystemObject|컴퓨터 파일 시스템에 엑세스할 수 있음|
|Function|새 함수를 만듦|
|Global|Global 메서드들을 하나의 개체로 모으는 내부 개체|
|Math|기본적인 계산 기능과 상수를 제공하는 내부 개체|
|Number|숫자 상수의 Number 데이터 형식과 자리 표시자를 나타내는 개체|
|Object|모든 JScript 개체에 공통적인 기능을 제공|
|RegExp|정규식 패턴 검색에 관한 정보를 저장|
|Regular Expression|정규식 패턴을 포함|
|String|텍스트 문자열을 조작하고 서식을 지정하거나 문자열 안에서 부분 문자열을 결정하고 위치를 지정할 수 있음|
|VBArray|Visual Basic 안전 배열에 엑세스할 수 있음|
   
<br />
### Operator   
// 연산자   
   
|Language element|Description|
|:---|:---|
|? :|조건에 따라 두 식 중 하나를 수행 (삼항 trinomial)|
|--|변수를 1씩 감소|
|!=|두 식을 비교하여 서로 다른 값을 갖는지 판단|
|==|두 식을 비교하여 서로 같은 값을 갖는지 판단|
|*|두 수를 곱함|
|/|두 수를 나눈 결과를 반환|
|%|두 수를 나눈 후 나머지를 반환|
|!|한 식에 논리 부정을 수행|
|\|\||두 식에 논리합을 수행|
|&&|두 식에 논리곱을 수행|
|-|수식의 음수 값을 나타냄|
|+|두 수를 더하거나 문자열을 연결|
|===|두 식을 비교하여 서로 값과 데이터 형식이 같은지 판단|
|<=|두 식을 비교하여 어느 쪽이 더 작거나 같은지 판단|
|<|두 식을 비교하여 어느 쪽이 더 작은지 판단|
|>=|두 식을 비교하여 어느 쪽이 더 크거나 같은지 판단|
|>|두 식을 비교하여 어느 쪽이 더 큰지 판단|
|!==|두 식을 비교하여 서로 값과 데이터 형식이 다른지 판단|
|&|두 식에 비트 논리곱을 수행|
|∧|두 식에 비트 배타적 논리합 연산을 수행|
|~|식에 비트 부정 연산을 수행|
|＞＞|부호를 바꾸지 않고 식을 비트 단위로 오른쪽으로 옮김|
|＜＜|식을 비트 단위로 왼쪽으로 옮김|
|\||두 식에 비트 논리합을 수행|
|-|두 식을 뺌|
|,|두 식을 순차적으로 수행|
|＞＞＞|부호 없이 식을 비트 단위로 오른쪽으로 옮김|
|++|변수를 1씩 증가시킴|
|=|변수에 값을 지정|
|delete|개체의 속성을 삭제하거나 배열에서 요소를 제거|
|instanceof|개체가 특정 클라스의 인스턴스인지 여부를 나타내는 부울값을 반환|
|new|새 개체를 만듦|
|typeof|식의 데이터 형식을 나타내는 문자열을 반환|
|void|식이 값을 반환하지 않도록 함|

<br />
### 복합 지정 연산자   
   
|Language element|Description|
|:---|:---|
|+=|변수를 지정한 양만큼 증가|
|&=|식에 비트 논리곱 연산을 수행|
|\|=|식에 비트 논리합 연산을 수행|
|∧=|식에 비트 배타적 논리합 연산을 수행|
|/=|식을 변수로 나눔|
|＜＜=|식을 비트 단위로 왼쪽으로 옮김|
|%=|두 수를 나눈 후 나머지만 반환|
|*=|임의의 수를 다른 수에 곱함|
|＞＞=|부호를 바꾸지 않고 식을 비트 단위로 오른쪽으로 옮김|
|-=|변수에서 식의 값을 뺌|
|＞＞＞=|부호 없이 변수를 비트 단위로 오른쪽으로 옮김|

<br />
### 비교 연산자   
   
- 비교 결과를 나타내는 부울값을 반환   
- JScript에서 문자열을 비교할 때는 해당 문자식의 유니코드 문자 값을 사용함   
   
- expression1과 expression2의 형식 및 값에 따라 서로 다른 연산자 그룹이 작용하는 방식   
   
|Language element|작용하는 방식|
|:---|:---|
|관계<br /><, >, <=, >=|- expression1과 expression2를 모두 숫자로 변환<br />- 두 식이 모두 문자열이면 사전순으로 문자열을 비교<br />- 두 식이 모두 NaN이면 false를 반환<br />- Negative 0은 Positive 0과 같음<br />- Negative Infinity는 자신을 포함한 모든 것보다 작음<br />- Positive Infinity는 자신을 포함한 모든 것보다 큼|
|같음<br />==, !=|- 두 식의 형식이 다르면 문자열이나 숫자 또는 부울값으로 변환<br />- NaN은 자신을 포함한 모든 것과 같지 않음<br />- Negative 0은 Positive 0과 같음<br />- null은 null 및 undefined와 같음<br />- 문자열이 서로 같거나, 숫자의 크기가 같거나, 개체가 같거나, 부울값이 일치하거나, 형식이 다른 경우 이들 상황 중 하나로 강제 변환할 수 있으면 두 값은 같은 것으로 간주됨<br />- 그 외의 다른 경우에는 두 값이 다른 것으로 간주됨|
|동치<br />===, !==|- 이 연산자는 형식 변환이 되지 않는 점을 제외하면 기본적으로 같음. 연산자와 동일하게 작용하지만 두 식이 같은 것으로 간주되려면 형식도 일치해야 함|
   
<br />
### Property   
// 속성   
   
|Language element|Description|
|:---|:---|
|$1...$9|패턴 일치 과정에서 찾아 저장된 최근 9개 부분을 반환|
|arguments|현재 실행 중인 함수에 전달된 각 인수를 포함하는 배열을 반환|
|caller|현재 함수를 불러온 함수에 대한 참조를 반환|
|constructor|개체를 만드는 함수를 지정|
|description|특정 오류와 관련된 설명적인 문자열을 반환하거나 설정|
|E|자연 로그의 밑인 오일러 상수를 반환|
|index|검색한 문자열에서 처음으로 일치하는 부분이 시작하는 문자 위치를 반환|
|Infinity|Number.POSITIVE_INFINITY의 초기 값을 반환|
|input|검색하는 데 사용한 문자열을 반환|
|lastIndex|검색한 문자열에서 마지막으로 일치하는 부분이 시작하는 문자 위치를 반환|
|length (Array)|배열에 정의된 요소의 최고값보다 하나 큰 정수값을 반환|
|length (Function)|함수에 정의된 인수의 개수를 반환|
|length (String)|String 개체의 길이를 반환|
|LN2|자연 로그 2를 반환|
|LN10|자연 로그 10을 반환|
|LOG2E|밑이 2인 로그 e (오일러 상수) 를 반환|
|LOG10E|밑이 10인 로그 e (오일러 상수) 를 반환|
|MAX_VALUE|JScript에서 나타낼 수 있는 가장 큰 수를 반환|
|MIN_VALUE|JScript에서 나타낼 수 있는 0에 가장 가까운 수를 반환|
|NaN (Global)|식이 숫자가 아님을 나타내는 특수 값 (NaN) 을 반환|
|NaN (Number)|식이 숫자가 아님을 나타내는 특수 값 (NaN) 을 반환|
|NEGATIVE_INFINITY|JScript에서 나타낼 수 있는 가장 큰 음수 (-Number.MAX_VALUE) 보다 큰 음수 값을 반환|
|number|특정 오류와 관련된 숫자 값을 반환하거나 설정|
|PI|원주율의 근사치 3.141592653589793을 반환|
|POSITIVE_INFINITY|JScript에서 나타낼 수 있는 가장 큰 양수 (Number.MAX_VALUE) 보다 큰 값을 반환|
|prototype|개체 클래스의 초기 설정에 대한 참조를 반환|
|source|정규식 패턴의 텍스트 복사본을 반환|
|SQRT1_2|0.5의 제곱근 또는 1을 2의 제곱근으로 나눈 값을 반환|
|SQRT2|2의 제곱근을 반환|

<br />
### Statement   
// 문   
   
|Language element|Description|
|:---|:---|
|@cc_on|// 조건부 컴파일 지원 기능을 활성화<br />- Enable conditional compilation support|
|// (a line of comment)|JScript 구문 분석기에서 한 줄로 된 주석문을 무시하도록 함|
|/* ... */ (a number of lines of comment)|JScript 구문 분석기에서 여러 줄로 된 주석문을 무시하도록 함|
|@if|식의 값에 따라 조건에 맞는 문 그룹을 실행|
|@set|// 조건부 컴파일 문에 사용할 변수들을 만듦<br />- Create variables for conditional compilation statements|
|break|현재 루프를 종료하거나 label로 연결된 경우에는 연결된 문을 종료|
|catch|try 블록 안의 코드에 오류가 발생하면 실행할 문을 포함시킴|
|continue|현재 루프 반복을 중지하고 새로 반복을 시작함|
|do...while|문 블록을 한번 실행한 후 조건식이 false가 될 때까지 루프를 반복 실행|
|for|개체나 배열의 각 요소에 대해 하나 이상의 문을 실행|
|for...in|개체의 각 속성이나 배열의 각 요소에 대해 하나 이상의 문을 실행|
|function|// 새 함수를 선언<br />- Declare a new function|
|if...else|식의 값에 따라 조건에 맞는 문 그룹을 실행|
|Labeled|문에 식별자를 제공|
|return|현재 함수를 종료하고 그 함수에서 구한 값을 반환|
|switch|지정한 식의 값이 레이블과 일치하면 하나 이상의 문을 실행할 수 있음|
|this|현재 개체를 참조|
|throw|try...catch 문에서 처리할 수 있는 오류 조건을 만듦|
|try|JScript 오류를 처리|
|var|변수를 선언|
|while|지정한 조건이 false가 될때까지 문을 실행|
|with|문의 기본 개체를 설정|
   
<br />
### Runtime Error List   
// 런타임 오류 목록   
   
|Error Number|Description|
|:---|:---|
|5|프로시저 호출 또는 인수가 잘못되었습니다|
|6|숫자가 너무 큽니다|
|7|메모리가 부족합니다|
|9|첨자 사용이 잘못되었습니다|
|10|배열이 고정되었거나 일시적으로 잠금 상태입니다|
|11|0으로 나누었습니다|
|13|형식이 일치하지 않습니다|
|14|문자열 공간이 부족합니다|
|17|요청한 작업을 수행할 수 없습니다|
|28|스택 공간이 부족합니다|
|35|Sub 또는 Function이 정의되지 않았습니다|
|48|DLL 로드 중 오류가 발생하였습니다|
|51|내부 오류입니다|
|52|파일 이름 또는 번호가 잘못되었습니다|
|53|파일이 없습니다|
|54|파일 모드가 잘못되었습니다|
|55|파일이 이미 열려 잇습니다|
|57|장치 입/출력 오류입니다|
|58|파일이 이미 존재합니다|
|61|디스크에 여유 공간이 없습니다|
|62|파일 끝을 넘는 입력(값)입니다|
|67|파일이 너무 많습니다|
|68|사용할 수 없는 장치입니다|
|70|사용 권한이 없습니다|
|71|디스크가 준비되지 않았습니다|
|74|다른 드라이브로 이름을 바꿀 수 없습니다|
|75|경로/파일 엑세스 오류입니다|
|76|경로를 찾을 수 없습니다|
|91|Object 변수나 With 변수가 설정되어 있지 않습니다|
|92|For 루프를 초기화하지 않았습니다|
|94|null의 사용이 잘못되었습니다|
|322|필요한 임시 파일을 만들 수 없습니다|
|424|개체가 필요합니다|
|429|자동화 서버는 개체를 만들 수 없습니다|
|430|클래스가 자동화를 지원하지 않습니다|
|432|자동화 실행 중 파일 이름이나 클래스 이름을 찾을 수 없습니다|
|438|개체가 이 속성 또는 메서드를 지원하지 않습니다|
|440|자동화 오류가 발생하였습니다|
|445|개체가 이 동작을 지원하지 않습니다|
|446|개체가 명명된 인수를 지원하지 않습니다|
|447|개체가 현재의 로케일 설정을 지원하지 않습니다|
|448|명명된 인수를 찾을 수 없습니다|
|449|선택적인 인수가 아닙니다|
|450|인수의 개수나 속성 지정이 잘못되었습니다|
|451|컬렉션이 아닌 개체입니다|
|453|지정한 DLL함수를 찾을 수 없습니다|
|458|변수가 JScript에서 지원하지 않는 자동화 형식을 사용하고 있습니다|
|462|원격 서버 시스템이 없거나 사용할 수 없습니다|
|501|변수를 지정할 수 없습니다|
|502|개체를 스크립트하는데 잘못되었습니다|
|503|개체를 초기화하느데 잘못되었습니다|
|504|개체를 만드는데 잘못되었습니다|
|507|예외가 발생하였습니다|
|5000|'여기'에 정의할 수 없습니다|
|5001|숫자가 필요합니다|
|5002|함수가 필요합니다|
|5003|함수 결과에 지정할 수 없습니다|
|5004|개체 인덱스 작업을 할 수 없습니다|
|5005|문자열이 필요합니다|
|5006|Date 개체가 필요합니다|
|5007|개체가 필요합니다|
|5008|지정이 잘못되었습니다|
|5009|식별자가 정의되지 않았습니다|
|5010|Boolean이 필요합니다|
|5011|지워진 스크립트에서 코드를 실행할 수 없습니다|
|5012|개체 구성원이 필요합니다|
|5013|VBArray가 필요합니다|
|5014|JScript 개체가 필요합니다|
|5015|Enumerator 개체가 필요합니다|
|5016|정규식 개체가 필요합니다|
|5017|정규식에 구문 오류가 있습니다|
|5018|예기치 않은 한정 기호입니다|
|5019|정규식에 ']'가 필요합니다|
|5020|정규식에 ')'가 필요합니다|
|5021|문자 집합의 범위가 틀립니다|
|5022|예외가 발생하여 해결할 수 없습니다|
|5023|함수에 유효한 프로토타입 개체가 없습니다|

<br />
### Syntax Error List   
// 구문 오류 목록   
   
|Error Number|Description|
|:---|:---|
|1001|메모리가 부족합니다|
|1002|구문 오류입니다|
|1003|':'이 필요합니다|
|1004|';'이 필요합니다|
|1005|'('가 필요합니다|
|1006|')'가 필요합니다|
|1007|']'가 필요합니다|
|1008|'{'가 필요합니다|
|1009|'}'가 필요합니다|
|1010|식별자가 필요합니다|
|1011|'='가 필요합니다|
|1012|'/'가 필요합니다|
|1013|유효하지 않은 숫자입니다|
|1014|유효하지 않은 문자입니다|
|1015|종료되지 않은 문자열 상수입니다|
|1016|종료되지 않은 주석입니다|
|1018|'return'문이 함수 밖에 있습니다|
|1019|루프 밖에서는 'break'를 사용할 수 없습니다|
|1020|루프 밖에서는 'continue'를 사용할 수 없습니다|
|1023|16진수가 필요합니다|
|1024|'while'이 필요합니다|
|1025|레이블이 다시 정의되었습니다|
|1026|레이블이 없습니다|
|1027|'switch'문에서 'default'는 한 번만 사용할 수 있습니다|
|1028|식별자나 문자열이 필요합니다|
|1029|'@end'가 필요합니다|
|1030|조건부 컴파일이 해제되었습니다|
|1031|상수가 필요합니다|
|1032|'@'이 필요합니다|
|1033|'catch'가 필요합니다|
|1034|'var'가 필요합니다|
|1035|'throw' 다음에 동일한 원본 줄에 있는 식이 있어야 합니다|
   
<br />
### Data format conversion   
// 데이터 형식 변환   
   
// JScript의 데이터 형식 자동 변환에 대한 설명   
- Description of JScript's automatic conversion of data formats   
   
- 언어에서 사용하는 데이터 형식은 모두 6가지이며 모든 값은 다음 중 한가지 형식을 가짐   
  - undefined : undefined라는 한 가지 값을 가짐   
  - null : numm이라는 한 가지 값을 가짐   
  - Boolean : 두 가지 논리값 true와 false를 나타냄   
  - String : 작은따옴표 또는 큰 따움표 사이의 문자열은 0개 이상의 유니코드 문자를 갖음. 빈 문자열("")의 문자와 길이는 0임   
  - Number : 숫자는 IEEE 754 규칙에 따라 정수 또는 부동 소수점 숫자임. 또한 다음과 같은 특수값들도 있음   
    - NaN, 숫자가 아님 (Not a Number)   
    - Positive Infinity   
    - Negative Infinity   
    - Positive 0   
    - Negative 0   
  - Object : 개체 형식은 개체의 속성과 메서드를 설정한 개체 정의임   
   
- 아래 표는 컨텍스트가 JScript에 어떤 데이터 형식을 다른 형식으로 변환하도록 요구했을 때 어떤 일이 발생하는지를 정의한 것임   
   
|Output Data<br />↓|Input Data<br />→||||||
|:---:|:---|:---|:---|:---|:---|:---|
||Undefined|null|Boolean|Number|String|Object|
|boolean|false|false|변환 안됨|+0, -0, NaN 중 하나이면 false, 그렇지 않으면 true|빈 문자열 ("") 이면 false, 그렇지 않으면 true|true|
|number|NaN|NaN|true이면 1, false이면 +0|변환 안됨|숫자로 해석될 수 없으며 NaN으로 해석됨|Number 개체|
|string|"undefined"|"null"|"true" 또는 "false"|부호를 포함한 숫자의 절대값이며 아래 사항은 예외임<br />- NaN은 "NaN"을 반환함<br />- +0 또는 -0은 "0"을 반환함<br />- + 무한대는 "Infinity"를 반환함<br />- - 무한대는 "-Infinity"를 반환함|변환 안됨|String 개체|
|object|런타임 오류|런타임 오류|새 Boolean 개체|새 Number 개체|새 String 개체|변환 안됨|
   
<br />
### Regular Expression Syntax   
// 정규식 구문   
   
// 정규식 패턴을 지정할 때 사용하는 특수 문자 및 시퀀스의 목록   
- List of special characters and sequences used to specify regular expression patterns   
   
|Character|Description|
|:---|:---|
|\ |다음에 오는 문자를 특수 문자나 리터럴로 표시함. 예를 들어, "n"은 문자 "n"과 일치함. "\n"은 줄 바꿈 문자와 일치함. 시퀀스 "\\ \\"은 "\\"와 같고, "\\("는 "("와 같음|
|∧|입력의 시작 부분을 찾음|
|$|입력의 끝 부분을 찾음|
|*|앞에 오는 문자를 0번 이상 찾음. 예를 들어, "zo*"를 입력하면 "z" 또는 "zoo"를 찾음|
|+|앞에 오는 문자를 1번 이상 찾음. 예를 들어, "zo+"를 입력하면 "zoo"를 찾지만 "z"는 여기에 포함되지 않음|
|?|앞에 오는 문자를 0번 이상 찾음. 예를 들어, "a? ve?"를 입력하면 "never"에 있는 "ve"를 찾음|
|.|줄바꿈 문자를 제외한 단일 문자를 찾음|
|(pattern)|pattern을 찾고 일치하는 내용을 기억함. 일치하는 부분 문자열은 Item[0]...[n]을 사용하여 결과로 나오는 Matches 컬렉션에서 검색할 수 있음. 괄호 문자 () 를 찾으려면 "\\(" 또는 "\\)"를 사용함|
|x\|y|x 또는 y를 찾음. 예를 들어, "z\|food"는 "z" 또는 "food"를 찾음. "(z\|f)ood"로는 "zoo"나 "food"를 찾을 수 있음|
|{n}|n은 음이 아닌 정수임. 정확하게 n번 일치하는 부분을 찾음. 예를 들어, "o{2}"는 "Bob"의 "o"를 찾지 않지만 "foooood"의 처음 두 o를 찾음|
|{n,}|n은 음이 아닌 정수임. 적어도 n번 일치하는 부분을 찾음. 예를 들어, "o{2,}"는 "Bob"의 "o"를 찾지만 "foooood"의 o는 모두 찾음. "o{1,}"은 "o+"와 같음. "o{0,}"은 "o*"과 같음|
|{n,m}|m과 n은 음이 아닌 정수임. 최소 n번, 최대 m번 일치하는 부분을 찾음. 예를 들어, "o(1,3}"은 "foooood"의 처음 세 o를 찾음. "o{0,1}"은 "o?"와 같음|
|[xyz]|문자 집함임. 괄호 안의 문자 중 하나를 찾음. 예를 들어, "[abc]"는 "plain"의 "a"를 찾음|
|[∧xyz]|문자 집합에 없는 문자를 찾음. 괄호 안에 있지 않은 문자 중 하나를 찾음. 예를 들어, "[∧abc]"는 "plain"의 "p"를 찾음|
|[a-z]|문자 범위임. 지정한 범위에 있는 문자 중 하나를 찾음. 예를 들어, "[a-z]"는 "a"에서 "z"까지의 알파벳 소문자를 찾음|
|[∧m-z]|지정한 문자 범위가 아닌 집합임. 지정한 범위에 있지 않은 문자 중 하나를 찾음. 예를 들어, "[m-z]"는 "m"에서 "z"까지에 없는 문자를 찾음|
|\b|단어의 경계, 즉 단어와 공백 사이의 위치를 찾음. 예를 들어, "er\b"는 "never"의 "er"를 찾지만 "verb"의 "er"는 찾지 않음|
|\B|단어의 경계에 있지 않은 문자를 찾음. "ea*r\B"는 "never early"의 "ear"을 찾음|
|\d|숫자를 찾음. [0-9]와 같음|
|\D|숫자가 아닌 문자를 찾음. [∧0-9]와 같음|
|\f|용지 공급 문자를 찾음|
|\n|줄 바꿈 문자를 찾음|
|\r|캐리지 리턴 문자를 찾음|
|\s|공백, 탭, 용지 공급 등 모든 종류의 공백 문자를 찾음. "[\f\n\r\t\v]"와 같음|
|\S|공백 문자가 아닌 문자를 찾음. "[∧\f\n\r\t\v]"와 같음|
|\t|탭 문자를 찾음|
|\v|세로 탭 문자를 찾음|
|\w|밑줄을 포함한 모든 단어 문자를 찾음. "[A-Za-z0-9_]"와 같음|
|\W|단어가 아닌 문자를 찾음. "[∧A-Za-z0-9_]"와 같음|
|\num|num을 찾음. 여기서 num은 양의 정수임. 이전에 참조한 값을 다시 참조함. 예를 들어, "(.)\1"은 연속적으로 같은 문자가 두 번 나오는 것을 찾음|
|\n|n을 찾음. 여기서 n은 8진 제어 값임. 8진 제어 값은 1, 2, 3 자리 중 하나라야 함. 예를 들어, "\11"과 "\011"은 모두 탭 문자를 나타내지만 "\0011"은 "\001" & "1"과 같음. 8진 제어 값은 256을 넘을 수 없음. 이 값이 256을 넘는 경우에는 처음 두 자릿수 만이 식을 구성함. 정규식에 ASCII 코드를 사용할 수 있음|
|\xn|n을 찾음. 여기서 n은 16진 제어 값임. 16진 제어 값은 정확히 두 자리이어야 함. 예를 들어, "\x41"은 "A"에 해당하지만 "\x041"은 "\x04" & "1"과 같음. 정규식에 ASCII 코드를 사용할 수 있음|
   
<br />
### Conditional Compilation   
// 조건부 컴파일   
   
// JScript의 새로운 기능들을 지원하지 않는 브라우저와도 호환성을 유지하며 새로운 기능들을 사용할 수 있음   
- JScript's new features remain compatible with browsers that do not support new features and new features are available   
   
- 조건부 컴파일 기능은 @cc_on 문을 사용하거나 주석 외부에 @if 또는 @set 문을 사용하여 활성화됨   
- 조건부 컴파일은 보통 JScript의 새 기능을 사용하거나, 스크립트에 디버깅 지원을 포함하거나, 코드 실행을 추적할 때 주로 사용함   
- 조건부 컴파일 코드는 가능한 주석 내부에 두는 것이 좋음   
   
- 아래 예시에서는 @cc_on 문으로 조건부 컴파일 기능이 활성화된 경우에만 사용되는 특수한 주석 구분 기호를 사용하고 있음. 조건부 컴파일을 이해하지 못하는 스크립팅 엔진에서는 새 스크립팅 엔진이 필요하다는 내용의 메시지만 나옴   
   
```c
/*@cc_on @*/
/*@if (@_jscript_version == 4)
    alert("JScript 버전 4");
    @else @*/
    alert("최신 스크립팅 엔진을 사용하십시오.");
/*@end @*/
```
   
<br />
### Conditional Compilation Variables   
// 조건부 컴파일 변수   
   
// 조건부 컴파일에 사용되는 사전 정의된 변수 목록   
// true가 아니 변수는 정의된 것이 아니며 엑세스하면 NaN으로 작용함   
- List of predefined variables used for conditional compilation   
- The non-true variable is not defined and will act as NaN if accessed   
   
|Variable|Description|
|:---|:---|
|@_win32|Win32 시스템에서 실행하면 true임|
|@_win16|Win16 시스템에서 실행하면 true임|
|@_mac|Apple Macintosh 시스템에서 실행하면 true임|
|@_alpha|DEC Alpha 프로그램에서 실행하면 true임|
|@_x86|Intel 프로세서에서 실행하면 true임|
|@_mc680x0|Motorola 680x0 프로세서에서 실행하면 true임|
|@_PowerPC|Motorola PowerPC 프로세스에서 실행하면 true임|
|@_jscript|항상 true임|
|@_jscript_build|JScript 스크립팅 엔진 작성 번호를 포함함|
|@_jscript_version|주 번호. 보조 번호 형식의 JScript 버전 번호를 포함함|
   
<br />
### Scripting runtime library   
// Scripting 런타임 라이브러리   
   
|Category|Type|Language element|Description|
|:---|:---|:---|:---|
|컬렉션|Object|Drives|사용할 수 있는 모든 드라이브의 읽기 전용 컬렉션임|
|컬렉션|Object|Files|폴더 안에 있는 모든 File 개체의 컬렉션임|
|컬렉션|Object|Folders|Folder 안에 있는 모든 Folder 개체의 컬렉션임|
|데이터 저장소|Object|Dictionary|데이터 키-항목 쌍을 저장하는 개체임|
|사전|Method|Add|Dictionary 개체에 키-항목 쌍을 추가|
|사전|Method|Exists|Dictionary 개체에 지정한 키가 있으면 true를, 그렇지 않으면 false를 반환|
|사전|Method|Items|Dictionary 개체에의 항목을 모두 포함한 배열을 반환|
|사전|Method|Keys|Dictionary 개체의 기존 키를 모두 포함한 배열을 반환|
|사전|Method|Remove|Dictionary 개체에서 키-항목 쌍을 하나 제거|
|사전|Method|RemoveAll|Dictionary 개체에서 키-항목 쌍을 모두 제거|
|사전|Property|Count|컬렉션이나 Dictionary 개체의 항목 수를 반환|
|사전|Property|Item|Dictionary 개체에서 지정한 key에 해당하는 item을 설정하거나 반환|
|사전|Property|Key|Dictionary 개체의 key를 설정|
|파일 시스템|Object|Drive|특정 디스크 드라이브나 네트워크 공유 속성에 엑세스할 수 있음|
|파일 시스템|Object|File|파일의 모든 속성에 엑세스할 수 있음|
|파일 시스템|Object|FileSystemObject|컴퓨터의 파일 시스템에 엑세스할 수 있음|
|파일 시스템|Object|Folder|폴더의 모든 속성에 엑세스할 수 있음|
|파일 시스템|Object|TextStream|파일에 순차적으로 쉽게 엑세스함|
|FileSystemObject|Method|BuildPath|기존 경로에 이름을 추가|
|FileSystemObject|Method|CopyFile|하나 이상의 파일을 기존 위치에서 다른 위치로 복사|
|FileSystemObject|Method|CopyFolder|폴더를 기존 위치에서 다른 위치로 반복 복사|
|FileSystemObject|Method|CreateFolder|폴더를 만듦|
|FileSystemObject|Method|CreateTextFile|지정한 파일 이름을 만들고 그 파일을 읽거나 쓰는데 사용할 수 있는 TextStream 개체를 반환|
|FileSystemObject|Method|DeleteFile|지정한 파일을 삭제|
|FileSystemObject|Method|DeleteFolder|지정한 폴더와 그 내용을 삭제|
|FileSystemObject|Method|DriveExists|지정한 드라이브가 있으면 true를, 그렇지 않으면 false를 반환|
|FileSystemObject|Method|FileExists|지정한 파일이 있으면 true를, 그렇지 않으면 false를 반환|
|FileSystemObject|Method|FolderExists|지정한 폴더가 있으면 true를, 그렇지 않으면 false를 반환|
|FileSystemObject|Method|GetAbsolutePathName|주어진 경로에서 정확한 전체 경로를 반환|
|FileSystemObject|Method|GetBaseName|주어진 경로에서 파일의 기본 이름 (모든 파일 확장명 제외) 이나 폴더를 포함한 문자열을 반환|
|FileSystemObject|Method|GetDrive|지정한 경로에서 드라이브에 해당하는 Drive 개체를 반환|
|FileSystemObject|Method|GetDriveName|지정한 경로에서 드라이브 이름을 포함한 문자열을 반환|
|FileSystemObject|Method|GetFile|지정한 경로에서 파일에 해당하는 File 개체를 반환|
|FileSystemObject|Method|GetExtensionName|경로의 마지막 구성 요소에 해당하는 확장명 이름을 포함한 문자열을 반환|
|FileSystemObject|Method|GetFileName|드라이브 정보의 일부분이 아닌 지정한 경로에서 마지막 파일 이름이나 폴더를 반환|
|FileSystemObject|Method|GetFolder|지정한 경로에서 폴더에 해당하는 Folder 개체를 반환|
|FileSystemObject|Method|GetParentFolderName|지정한 경로에서 마지막 파일이나 폴더의 상위 폴더 이름을 포함한 문자열을 반환|
|FileSystemObject|Method|GetSpecialFolder|지정한 특정 폴더를 반환|
|FileSystemObject|Method|GetTempName|임의로 만든 임시 파일이나 폴더 이름을 반환|
|FileSystemObject|Method|MoveFile|하나 이상의 파일을 기존 위치에서 다른 위치로 옮김|
|FileSystemObject|Method|MoveFolder|하나 이상의 폴더를 기존 위치에서 다른 위치로 옮김|
|FileSystemObject|Method|OpenTextFile|지정한 파일을 열고 그 파일에서 읽거나, 쓰거나, 추가하는 데 사용할 수 있는 TextStream 개체를 반환|
|FileSystemObject|Property|Drives|로컬 컴퓨터에서 사용할 수 있는 모든 Drive 개체로 구성된 Drives 컬렉션을 반환|
|드라이브|Property|AvailableSpace|지정한 드라이브나 네트워크 공유 영역에서 사용자가 사용할 수 있는 공간의 크기를 반환|
|드라이브|Property|Count|컬렉션이나 Dictionary 개체의 항목 수를 반환|
|드라이브|Property|DriveLetter|실제 로컬 드라이브나 네트워크 공유 영역의 드라이브 문자를 반환|
|드라이브|Property|DriveType|지정한 드라이브의 형식을 나타내는 값을 반환|
|드라이브|Property|FileSystem|지정한 드라이브에서 사용하는 파일 시스템의 형식을 반환|
|드라이브|Property|FreeSpace|지정한 드라이브나 네트워크 공유 영역에서 사용할 수 있는 사용 가능한 공간의 크기를 반환|
|드라이브|Property|IsReady|지정한 드라이브가 준비되면 true를, 그렇지 않으면 false를 반환|
|드라이브|Property|Item|Dictionary 개체에서 지정한 key에 해당하는 item을 설정하거나 반환|
|드라이브|Property|RootFolder|지정한 드라이브의 루트 폴더를 나타내는 Folder 개체를 반환|
|드라이브|Property|SerialNumber|디스크 볼륨을 고유하게 나타내는 데 사용하는 일련 번호를 십진수로 반환|
|드라이브|Property|ShareName|지정한 드라이브의 네트워크 공유 이름을 반환|
|드라이브|Property|TotalSize|드라이브나 네트워크 공유 영역의 전체 공간을 바이트 단위로 반환|
|드라이브|Property|VolumeName|지정한 드라이브의 볼륨 이름을 설정하거나 반환|
|파일 폴더|Method|Add|Folders 컬렉션에 새 Folder를 추가|
|파일 폴더|Property|Attributes|파일이나 폴더의 특성을 설정하거나 반환|
|파일 폴더|Method|Copy|지정한 파일이나 폴더를 기존 위치에서 다른 위치로 복사|
|파일 폴더|Method|Delete|지정한 파일이나 폴더를 삭제|
|파일 폴더|Method|Move|지정한 파일이나 폴더를 기존 위치에서 다른 위치로 옮김|
|파일 폴더|Property|Count|컬렉션이나 Dictionary 개체의 항목 수를 반환|
|파일 폴더|Method|OpenAsTextStream|지정한 파일을 열고 그 파일을 읽거나, 쓰거나, 추가하는데 사용할 수 있는 TextStream 개체를 반환|
|파일 폴더|Property|DateCreated|지정한 파일이나 폴더가 만들어진 날짜와 시간을 반환|
|파일 폴더|Property|DateLastAccessed|지정한 파일이나 폴더에 마지막으로 엑세스한 날짜와 시간을 반환|
|파일 폴더|Property|DateLastModified|지정한 파일이나 폴더를 마지막으로 수정한 날짜와 시간을 반환|
|파일 폴더|Property|Drive|지정한 파일이나 폴더가 있는 드라이브의 드라이브 문자를 반환|
|파일 폴더|Property|Item|Dictionary 개체에서 지정한 key에 해당하는 item을 설정하거나 반환|
|파일 폴더|Property|ParentFolder|지정한 파일이나 폴더의 상위 폴더에 해당하는 Folder 개체를 반환|
|파일 폴더|Property|Name|지정한 파일이나 폴더의 이름을 설정하거나 반환|
|파일 폴더|Property|Path|지정한 파일, 폴더, 또는 드라이브의 경로를 반환|
|파일 폴더|Property|ShortName|예전 8.3 명명 규칙을 따르는 프로그램에서 사용되는 짧은 이름을 반환|
|파일 폴더|Property|ShortPath|예전 8.3 파일 명명 규칙을 따르는 프로그램에서 사용되는 짧은 경로를 반환|
|파일 폴더|Property|Size|지정한 파일이나 폴더의 크기를 바이트 단위로 반환|
|TextStream|Method|Close|열려있는 TextStream 파일을 닫음|
|TextStream|Method|Read|TextStream 파일에서 지정한 수만큼 문자를 읽고 결과로 나오는 문자열을 반환|
|TextStream|Method|ReadAll|TextStream 파일 전체를 읽고 결과로 나오는 문자열을 반환|
|TextStream|Method|ReadLine|TextStream 파일에서 줄 전체 (줄 바꿈 문자 앞까지, 줄 바꿈 문자는 제외) 를 읽고 결과로 나오는 문자열을 반환|
|TextStream|Method|Skip|TextStream 파일을 읽을 때 지정한 문자 수만큼 건너뜀|
|TextStream|Method|SkipLine|TextStream 파일을 읽을 때 다음 줄을 건너뜀|
|TextStream|Method|Write|TextStream 파일에 지정한 문자열을 씀|
|TextStream|Method|WriteBlankLines|TextStream 파일에 지정한 수만큼 줄 바꿈 문자를 씀|
|TextStream|Method|WriteLine|TextStream 파일에 지정한 문자열과 줄 바꿈 문자를 씀|
|TextStream|Property|AtEndOfLine|TextStream 파일의 줄 끝 표식 바로 앞에 파일 포인터가 있으면 true를, 그렇지 않으면 false를 반환|
|TextStream|Property|AtEndOfStream|TextStream 파일의 끝에 파일 포인터가 있으면 true를, 그렇지 않으면 false를 반환|
|TextStream|TextStream 파일의|Column|TextStream 파일에서 현재 문자가 있는 위치의 열 번호를 반환|
|TextStream|TextStream 파일의|Line|TextStream 파일에서 현재 줄 번호를 반환|
   
<br />
### JScript Term   
// JScript 용어   
   
#### constructor   
// 구성자   
   
// 다음 2가지의 특별한 기능을 가진 JScript 함수임   
// - JScript 함수는 new 연산자에 의해 호출됨   
// - JScript 함수는 this 키워드를 통해 새로 작성된 개체의 주소를 전달함   
// 새 개체를 초기화할 때 구성자를 사용   
- It is a JScript function with two special functions   
  - JScript function called by new operator   
  - The JScript function carries the address of a newly created object through this keyword   
- Use the Configurator when initializing a new object   
   
#### intrinsic object   
// 내부 개체   
   
// 표준 JScript 언어의 일부인 개체로, 모든 스크립트에서 사용할 수 있음   
// JScript 내부 개체에는 Array, Boolean, Data, Function, Global, Math, Number, Object, RegExp, Regular Expression, String이 있음   
- Objects that are part of the standard JScript language, available for all scripts   
- JScript intrinsic object types include Array, Boolean, Data, Function, Global, Math, Number, Object, RegExp, Regular Expression, String   
   
#### wrapper   
// 래퍼   
   
// 일부 다른 데이터 형식에 개체 스타일 인터페이스를 제공하기 위해 만든 개체   
// 래퍼 개체에는 Number 개체와 Boolean 개체가 있음   
- Objects created to provide object style interfaces to some other data formats   
- Wrapper object types include Number and Boolean objects   
   
#### local time   
// 로컬 시간   
   
// 스크립트를 실행하는 클라이언트나 서버의 시스템 시간   
- The system time of the client or server running the script   
   
#### locale   
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
   
#### run-time error   
// 런타임 오류   
   
// 코드 실행 중 발생하는 오류임   
// 프로그램의 문이 잘못된 연산을 시도할 때 발생함   
- This is an error that occurs during code execution   
- Runtime error occurs when a statement in a program attempts an incorrect operation   
   
#### string expression   
// 문자식   
   
// 일련의 연속적인 문자열을 평가하는 식   
// 문자식의 요소에는 문자열, 문자열 리터럴, String 개체 또는 문자열 변수를 반환하는 함수를 사용할 수 있음   
- An expression that evaluates a series of consecutive strings   
- An element of a character expression can use a function that returns a string, a string literal, a string object, or a string variable   
   
#### string comparison   
// 문자열 비교   
   
// 2개의 문자열을 비교함   
// 비교를 수행하는 함수에 지정하지 않으면 모든 문자열 비교는 이진으로 함   
// 영어의 경우 이진 비교는 대/소문자를 구분하지만 텍스트 비교는 대/소문자를 구분하지 않음   
- Compare two strings   
- All string comparisons are binary unless you specify a function that performs a comparison   
- For English, binary comparisons are case sensitive, but text comparisons are not case sensitive   
   
#### character code   
// 문자 코드   
   
// ASCII 문자 집합과 같이 특정 문자 집합을 나타내는 일련의 숫자   
- A series of numbers representing a particular set of characters, such as an ASCII character set   
   
#### scope   
// 범위   
   
// 변수, 프로시저, 또는 개체의 가시성을 정의함   
// 함수에서 선언된 변수들은 해당 함수 내에서만 볼 수 있고 호출과 호출 사이에는 값들을 잃음   
- Define the visibility of a variable, procedure, or object   
- Variables that are declared in a function are visible only within that function and lose values between calls   
   
#### variable   
// 변수   
   
// 이름으로 값을 저장하고 조정하는 데 사용하는 위치   
// JScript는 형식 제한이 적어서 스크립트 전체를 통해 변수 하나에 여러 종류의 데이터 형식을 사용할 수 있음   
- Where to store and adjust values by name   
- JScript has fewer format restrictions, allowing multiple types of data formats to be used for one variable throughout the script   
   
#### compound statement   
// 복합문   
   
// 중괄호 ({}) 로 묶이는 일련의 문   
// 문 하나를 써서 여러 작업을 수행해야 할 때 사용할 수 있음   
- A series of statements bound by brace ({})   
- Can be used when you need to do multiple things with one statement   
   
#### Boolean expression   
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
   
#### comparison operator   
// 비교연산자   
   
// 둘 이상의 값이나 식 사이의 관계를 나타내는 문자나 기호   
// 비교연산자에는 보다 작다 (<), 작거나 같다 (<=), 보다 크다 (>), 크거나 같다 (>=), 같지 않다 (!=), 같다 (==)가 있음   
- a character or symbol that represents a relationship between two or more values or expressions   
- Comparison operators have smaller (<), smaller or equal (<=), larger (>), larger or equal (>=), not equal (!==), and equal (==)   
   
#### Bitwise comparison   
// 비트 비교   
   
// 두 수식에서 같은 위치에 있는 비트를 비트별로 비교함   
- Bits in the same position are compared bit by bit in both equations   
   
#### user-defined object   
// 사용자 정의 개체   
   
// 원본 코드에서 사용자가 만드는 개체   
- Object created by the user in the source code   
   
#### property   
// 속성   
   
// 이름이 정해진 개체 특성   
// 속성은 크기, 색, 화면위치, 사용 또는 사용안함과 같은 개체의 상태 등 개체의 특성을 정의함   
- Named Object Properties   
- Attributes define an object's characteristics, such as size, color, screen location, and the state of the object, such as enabled or disabled   
   
#### numeric expression   
// 수식   
   
// 숫자로 평가될 수 있는 식   
// 식의 요소에는 숫자를 산출하는 키워드, 변수, 리터럴, 연산자의 조합이 포함됨   
// 경우에 따라 문자열도 가능하면 숫자로 변환됨   
- an expression that can be evaluated in numbers   
- Elements of an expression include a combination of keywords, variables, literals, and operators that produce numbers   
- In some cases, strings are also converted to numbers if possible   
   
#### expression   
// 식   
   
// 문자열, 숫자, 또는 개체를 만드는 키워드, 연산자, 변수, 리터럴의 조합   
// 계산을 하거나, 문자를 조정하거나, 함수를 호출하거나, 데이터를 테스트함   
- A combination of keywords, operators, variables, and literals that create a string, number, or object   
- Calculate, adjust characters, call functions, or test data   
   
#### primitive   
// 원시   
   
// JScript 언어의 일부이며, 값에 따라 조정되는 데이터 형식   
// JScript에서 원시로 간주하는 데이터 형식에는 Number, Boolean, String, Function이 있음   
// 개체와 배열은 원시 데이터 형식이 아님   
- Data type that is part of the JScript language and is adjusted according to the value   
- Data formats considered primitive by JScript include Number, Boolean, String, and Function   
- Objects and arrays are not in primitive data format   
   
#### Automation object   
// 자동화 개체   
   
// 자동화 인터페이스를 통해 다른 응용 프로그램이나 프로그래밍 도구에 노출되는 개체   
- Objects exposed to other applications or programming tools via the automation interface   
   
#### comment   
// 주석   
   
// 코드 사용법을 설명하기 위해 프로그래머가 코드에 추가하는 텍스트   
// JScript에서 주석줄은 보통 '//'로 시작함   
// 여러 줄로 된 주석문을 만들려면 ' /* '와 ' */ ' 구분 기호를 사용함   
- Text that the programmer adds to the code to explain how to use it   
- Comment line in JScript usually begins with '//'   
- Use ' /*' and ' */' delimiter to create multi-line comments   
   
#### class   
// 클래스   
   
// 개체의 형식을 정의   
// 런타임 시 개체의 인스턴스를 만드는 템플릿 역할을 함   
// 클래스는 개체의 속성과 그 개체의 동작을 제어하는 데 사용하는 메서드를 정의함   
- Define the type of object   
- Acting as a template for creating instances of objects at runtime   
- Class define the properties of an object and the methods used to control its behavior   
   
#### UTC (Universal Coordinated Time)   
// 협정 세계 표준시   
   
// WTS (세계 시간 표준) 이 설정한 시간   
// GMT (그리니치 표준시) 라고도 함   
- Time set by WTC (World Time Standard)   
- Also known as GMT (Greenwich Standard Time)   
   
#### ASCII Character set   
// ASCII 문자 집합   
   
// ASCII (정보 교환용 미국 표준 코드) 로 표준 영문 키보드에 있는 문자와 기호를 나타내는 데 사용하는 7비트 문자 집합   
// ASCII 문자 집합은 ANSI 문자 집합의 앞 부분에 나오는 128자 (0 ~ 127) 와 같음   
- A set of seven-bit characters used to represent characters and symbols on a standard English keyboard with ASCII (American Standard Code for Information Exchange)   
- ASCII character set is equal to 128 characters (0 ~ 127) in front of the ANSI character set   
   
#### Undefined   
// 정의되지 않음   
   
// 변수를 만든 후 변수에 값을 지정하기 전에 주어진 특별한 값   
- A special value given after creating a variable before specifying a value in the variable   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
