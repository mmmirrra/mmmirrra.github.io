---
layout: post
title:  "JScript: Internal Object"
date:   2024-03-14 09:00:00 +0900
categories: [JScript]
---

// JScript는 9가지 내부 (또는 "기본 제공") 개체를 제공함   
// 9가지 내부 개체란 구체적으로 Array, Boolean, Date, Function, Global, Math, Number, Object, String 개체를 말함   
// 각 내부 개체는 연관되어 있는 메서드와 속성을 가지고 있음   
- JScript provides nine internal (or "embedded") objects   
- Nine internal objects are specifically Array, Boolean, Date, Function, Global, Math, Number, Object, String objects   
- Each internal object has associated methods and properties   
   
<br />
### Array   
// Array 개체   
   
// JScript에서 개체는 배열로 다루고 배열은 개체로 다룸   
// 개체의 속성과 완전히 일치하는 배열의 아래 첨자는 숫자에 의해 참조될 수 있으며, 이름을 배열의 아래 첨자에 지정하면 이름에 의해 참조될 수 있음   
- In JScript, objects are treated as arrays and arrays are treated as objects   
- Subscripts in an array that completely match the properties of an object can be referenced by a number, and giving a name to a subscript in an array can be referenced by a name   
   
// 새 배열을 만들려면 아래 예시와 같이 new 연산자와 Array() 구성자를 사용함   
- To create a new array, use the new operator and the Array() configuration as in the example below   
   
```javascript
var theMonths = new Array(12) {
    theMonths[0] = "Jan";
    theMonths[1] = "Feb";
    theMonths[2] = "Mar";
    theMonths[3] = "Apr";
    theMonths[4] = "May";
    theMonths[5] = "Jun";
    theMonths[6] = "Jul";
    theMonths[7] = "Aug";
    theMonths[8] = "Sep";
    theMonths[9] = "Oct";
    theMonths[10] = "Nov";
    theMonths[11] = "Dec";
}
```
   
// Array 키워드를 사용하여 배열을 만들 때 JScript는 배열에 있는 항목의 수를 기록하는 length 속성을 배열에 포함함   
// 숫자를 지정하지 않으면 길이는 0으로 설정되며 배열은 어떤 항목도 가지지 않음   
// 숫자를 지정하면 길이는 지정한 숫자로 지정됨   
// 두 개 이상의 매개변수를 지정할 경우 매개변수는 배열에서 항목으로 사용되며 매개변수의 수는 아래 예시와 같이 length 속성에 지정되며 이것은 앞의 코드와 같음   
- When creating an array using the Array keyword, JScript includes length attributes in the array that record the number of items in the array   
- If a number is not specified, the length is set to 0, and the array does not have any entries   
- When a number is specified, the length is specified by the specified number   
- If more than one parameter is specified, the parameter is used as an item in the array, and the number of parameters is specified in the length property as shown in the example below, which is the same as the previous code   
   
```javascript
var theMonths = new Array("Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec");
```
   
// Array 키워드로 만든 배열에 요소에 추가하면 JScript는 length 값을 자동으로 변경함   
- When you add an element to an array created with the Array keyword, JScript automatically changes the length value   
   
<br />
### String   
// String 개체   
   
// JScript에서 문자열은 객체임   
// 이것은 문자열 변수를 선언하거나 문자열 리터럴을 사용할 때마다 실제로 사용자가 하고 있는 일은 새 문자열 개체를 만들고 있다는 의미임   
// String 개체는 문자열과 함께 사용할 수 있는 내부 메서드를 가지고 있음   
// 이 중 하나가 문자열의 일부분을 반환하는 substring 메서드임   
// 이 메서드는 숫자 두 개를 메서드의 인수로 사용함   
- In JScript, a string is an object   
- This means that every time you declare a string variable or use a string literal, what you're actually doing is creating a new string object   
- String object has an internal method that can be used with a string   
- One of these is a substring method that returns a portion of the string   
- This method uses two numbers as arguments for the method   
   
```javascript
aString = "0123456789";

// Specifies the achunk to "456"
var aChunk = aString.substring(4, 7);

// Specifies aNotherChunk to "456"
var aNotherChunk = aString.substring(7, 4);

// Use the previous example of creating an array
// Specifies the firstLetter variable to "J"
firstLetter = theMonths[5].substring(0, 1);
```
   
// String 개체의 다른 속성은 length 속성임   
// 이 속성은 문자열에서 문자 수를 포함하는데, 0은 빈 문자열을 의미함   
// 이것은 숫자 값이며 계산에 직접 사용할 수 있음   
- Another property of the String object is the length property   
- This property contains the number of characters in a string, where 0 means an empty string   
- This is a numeric value and can be used directly for calculation   
   
```javascript
// Specifies the howLong variable to 11
var howLong = "Hello World".length;
```
   
<br />
### Math   
// Math 개체   
   
// Math 개체는 모두 미리 정의된 속성과 메서드를 가지고 있음   
// 속성은 특정 숫자이며, 이 중의 하나가 pi값 (약 3.14159) 임   
// 다음 예시에서 알 수 있는 것처럼 이것은 Math.PI 속성임   
- Math objects all have predefined properties and methods   
- Attributes are specific numbers, one of which is a pi value (About 3.14159)   
- This is the Math.PI attribute, as shown in the following example   
   
```javascript
// The first letters of Math and PI are capital characters
var circleArea = Math.PI * radius * radius;
```
   
// Math 개체의 내부 메서드 중 하나는 지수 메서드, 즉, 어떤 숫자에 거듭제곱을 위첨자로 올려 놓는 pow 임   
// 아래 예시에서는 pi와 지수를 사용함   
- One of the internal methods of the Math object is an exponent method, i.e., a pow that places powers on a number as a superscript   
- In the examples below, pi and exponents are used   
   
```javascript
// The formula calculates the volume of a sphere with a given radius
volume = (4/3) * (Math.PI * Math.pow(radius, 3));
```
   
<br />
### Date Object   
// Date 개체   
   
// 오늘 날짜를 표시하거나 날짜들 사이의 차이를 계산하기 위하여 Date 개체를 사용함   
// 이 개체는 모두 미리 정의되어 있는 많은 속성과 메서드를 가지고 있음   
// 일반적으로 Date개체는 요일, 일, 월, 연도, 시, 분, 초를 제공함   
// 이 정보는 1970년 1월 1일, 00:00:00.000 GMT를 기준으로 하여 밀리초 단위까지 제공됨   
// 여기서 GMT는 "그리니치 표준시 (Greenwich Mean Time)" 를 의미함   
// 이 표현보다 좀 더 많이 사용하는 용어는 UTC 또는 "협정 세계 표준시"로, 이 시간은 WTS (World Time Standard-세계 시간 표준) 에서 나오는 신호를 말함   
- Use the Date object to display today's date or to calculate the difference between dates   
- This object all has many predefined properties and methods   
- Typically, Date objects provide days, days, months, years, hours, minutes, and seconds   
- This information is available in milliseconds as of 01 Jan 1970 00:00:00.000 GMT   
- GMT stands for "Greenwich Mean Time."   
- The term used more often than this is UTC or "Agreement World Standard Time", which is a signal from the World Time Standard (WTS)   
   
// JScript의 경우 시간은 1970년 1월 1일 자정부터 시작함   
// JScript는 그보다 더 이른 시간을 나타내는 Date 개체는 만들 수 없음   
// 더 이른 시간을 나타내려면 사용자 자신이 코드를 만들어야만 하는데 그것은 만만찮은 일임   
- For JScript, time starts at midnight on January 1, 1970   
- JScript cannot create a Date object that represents an earlier time   
- To indicate an earlier time, users have to create their own code, which is a daunting task   
   
// 새로운 Date 개체를 만들려면 new 연산자를 사용해야 함   
// 아래 예시에서는 현재 연도의 지나간 날짜 수와 남은 날짜 수를 계산함   
- New operator must be used to create a new Date object   
- The example below calculates the number of past and remaining dates for the current year   
   
```javascript
/*
    This example uses an array of previously defined month names.
    The first statement specifies today's date as "Day Month Date 00:00:00 Year" in the thisIsToday variable.
*/

var thisIsToday = new Date();

// 오늘 날짜로 변환함
// - Converted to today's date
var toDay = new Date();

// 연도, 월, 일 추출
// - Extract year, month, and day
var thisYear = toDay.getYEar() + 1900;
var thisMonth = theMonths[toDay.getMonth()];
var thisDay = thisMonth + " " + toDay.getDate() + "," + (parseInt(toDay.getYear()) + 1900);

// 시작일부터 날짜 수를 구함
// - Find the number of days from the start date
thisDay = MAth.round(Date.parse(thisDay) / 8.64e7);

// 한 해의 시작일에 대해 동일한 작업을 수행함
// - Performs the same task for the start date of the year
var firstDay = "1월 1일, " + thisYear;
firstDay = Math.floor(Date.parse(firstDay) / 8.64e7);

// 윤년이 될 경우를 대비하여 한 해의 마지막 날에 대하여 동일한 작업을 다시 함
// - The same work is done again on the last day of the year in case it becomes a leap year
var lastDay = "12월 31일, " + thisYear;
lastDay = Math.floor(Date.parse(lastDay) / 8.64e7);

// 해당 연도의 날짜 수를 계산
// - Calculate the number of days for the year
var daysInYear = (lastDay - firstDay) + 1;

// 경과한 날과 남은 날을 구함
// - Calculate the days elapsed and the days remaining
var daysElapsed = thisDay - firstDay;
var daysLeft = daysInYear - daysElapsed;

// 대부분의 연도에 대한 주석을 설정함
// - Set comments for most years
var comment1 = daysElapsed + "days have passed";
var comment2 = "This means that there are " + daysLeft + " days left in year " + thisYear + ".";

// 특별한 경우도 포함합니다 : 한 해의 시작과 마지막, 하루
// - Special cases include : the beginning, the end, and the day of the year
if (daysElapsed == 0) {
    comment1 = "January 1st, " + thisYear + ".";
}
if (daysElapsed == 1) {
    comment1 = "It's only been one day so far";
}
if (daysElapsed == daysInYear) {
    comment1 = thisYear + " has just passed";
}

if (daysLeft == 0) {
    comment2 = "I wish you all the best in the new year!";
}
if (daysLeft == 1) {
    comment2 = "There's only one day left in " + thisYear + ".";
}
if (daysLeft == daysInYear) {
    comment2 = "I wish you a happy new year!";
}
```
   
<br />
### Number   
// Number 개체   
   
// JScript는 Math 개체에서 사용할 수 있는 특별한 숫자 속성 (예 : PI) 뿐만 아니라 Number 개체를 통하여 몇 가지 다른 속성들을 제공함   
- JScript provides several other properties through Number objects, as well as special numeric properties (Example : PI) that can be used by Math objects   
   
|Property|Description|
|:---|:---|
|MAX_VALUE|// 가능한 가장 큰 숫자<br />// 약 1.79E+308<br />// 양수일 수도 있고 음수일 수도 있음<br />// 시스템마다 약간씩 다름<br />- The greatest possible number<br />- About 1.79E+308<br />- Can be positive or negative<br />- Slightly different from system to system|
|MIN_VALUE|// 가능한 가장 작은 숫자<br />// 약 2.22E-308<br />// 양수일 수도 있고 음수일 수도 있음<br />// 시스템마다 약간씩 다름<br />- The smallest possible number<br />- About 2.22E-308<br />- Can be positive or negative<br />- Slightly different from system to system|
|NaN|// 숫자가 아닌 특별한 값<br />- A special value, not a number|
|POSITIVE_INFINITY|// Number.MAX_VALUE보다 큰 양수는 모두 자동으로 이 값으로 변환됨<br />// "Inf"로 표시됨<br />- Any positive number greater than Number.MAX_VALUE is automatically converted to this value<br />- Marked as "Inf"|
|NEGATIVE_INFINITY|// -Number.MAX_VALUE보다 큰 음수는 모두 자동으로 이 값으로 변환됨<br />// "-Inf"로 표시됨<br />- Any negative number greater than -Number.MAX_VALUE is automatically converted to this value<br />- Marked as "-Inf"|
   
// Number.NaN은 "NaN (숫자 아님)" 으로 정의되는 특별한 속성임   
// 예를 들어 0으로 나누면 NaN을 반환함    
// 숫자로 구문 분석할 수 없는 문자열을 구문 분석할 때도 Number.NaN을 반환함   
// NaN은 어떤 숫자와도 다르며 그 자신과도 다름   
// NaN 결과를 검사하려면 Number.NaN과 비교하지 말고 isNaN() 함수를 사용해야 함   
- Number.NaN is a special property defined as "NaN (not a number)"   
- For example, dividing by 0 returns NaN   
- Returns Number.NaN when parsing strings that cannot be parsed by numbers   
- NaN is different from any number and is different from itself   
- To check NaN results, use the isNaN() function rather than compare to Number.NaN   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
