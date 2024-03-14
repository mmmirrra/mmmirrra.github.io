---
layout: post
title:  "JScript: Object"
date:   2024-03-14 09:00:00 +0900
categories: [JScript]
---

### Object definition   
// 개체 정의   
   
// JScript에서 개체란 본질적으로 속성과 메서드의 컬렉션임   
// 메서드는 개체의 한 구성원인 함수이고, 속성은 개체의 한 구성원인 하나의 값 또는 여러 값들의 집합임(하나의 배열이나 개체의 폼에서)   
// JScript는 내부 개체, 사용자 정의 개체, 브라우저 개체라는 3가지 종류의 개체를 지원함   
- In JScript, an object is essentially a collection of attributes and methods   
- A method is a function that is a member of an object, and an attribute is a value that is a member of an object or a set of values (in an array or form of an object)   
- JScript supports three types of objects: internal objects, custom objects, and browser objects   
   
### Objects used as arrays   
// 배열로 사용되는 개체   
   
// JScript에서는 개체와 배열을 동일한 것으로 취급함   
// 개체의 각 구성원(속성과 메서드)을 참조하려면 이름(개체명, 마침표(.), 속성명의 순서로 입력) 또는 배열 아래 첨자 인덱스를 사용하면 됨   
// JScript에서 아래 첨자는 0부터 번호를 매기기 시작함   
// 사용자 편의를 위해 아래 첨자는 아래 첨자의 이름으로도 참조할 수 있음   
- JScript treats objects and arrays as identical   
- To reference each member of an object (Properties and Methods), use a subscript index under the name (Enter object name, period (.), and attribute name in order) or array   
- In JScript, subscripts below begin to number from 0   
- For user convenience, subscripts below can also be referred to by the name of subscripts below   
   
// 따라서 여러가지 방법으로 속성을 참조할 수 있기 때문에 아래의 문은 동일한 효과를 나타냄   
- Therefore, the statements below show the same effect because you can refer to properties in many ways   
   
```javascript
theWidth = spaghetti.width;
theWidth = spaghetti[3];    // [3] is the "width" index
theWidth = spaghetti["width"];
```
   
// 숫자 인덱스로 속성을 참조할 경우 대괄호는 사용할 수 있지만 점(.)은 사용할 수 없음   
// 아래 문은 오류를 일으킴   
- If you reference properties by numeric index, brackets are available, but dots (.) are not   
- The statement below causes an error   
   
```javascript
theWidth = spaghetti.3; // Error occurred
```
   
// 한 개체가 다른 개체를 속성으로 사용할 경우 기존 명명 규칙을 그대로 적용함   
- Applies an existing naming convention if one object uses another as a property   
   
```javascript
// An array of shoppingLists is a property of toDoToDay
var init4 = toDoToday.shoppingList[3].substring(0, 1);
```
   
// 개체를 다른 개체의 속성으로 사용할 수 있다는 사실은 직접 지원되지 않는 둘 이상의 아래 첨자를 가진 배열을 만들 수 있다는 것을 의미함   
- The fact that an object can be used as a property of another object means that you can create an array with more than one subscript that is not directly supported   
   
// 아래 코드는 0 X 0부터 16 X 16까지의 곱셈표를 만듦   
- The code below creates a multiplication table from 0 X 0 to 16 X 16   
   
```javascript
// Create a cell to be tabulated
var multTable = new Array(17);
// Set rows
for (var j = 0; j < multTable.length; j++)
{
    // Create one row
    var aRow = new Array(17);
    // Sets the value for the row
    for(var i = 0; i < aRow.length; i++)
    {
        // Create a value and substitute it
        aRow[i] = (i + " times " + j + " = " + i*j);
    }
    // Arrange rows filled with values in the table
    multTable[j] = aRow;
}
```
   
// 이런 종류의 배열 요소 중 하나를 참조하려면 대괄호를 여러 개 사용함   
- Use multiple brackets to refer to one of these types of array elements   
   
```javascript
var multiply3x7 = multTable[3][7];
```
   
// 다음 문은 오류를 일으킴   
- The following statement causes an error   
   
```javascript
var multiply3x7 = multTable[3, 7];  // Error occurred
```
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
