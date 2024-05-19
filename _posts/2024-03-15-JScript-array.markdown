---
layout: post
title:  "JScript: Array"
date:   2024-03-15 09:00:00 +0900
categories: [JScript]
---

### Array Index   
// 배열 인덱스   
   
// JScript의 배열은 융통성이 있음   
// 어떤 배열의 요소가 세 개이고 인덱스 번호가 각각 0, 1, 2일 때 3에서 49까지 요소를 추가할 필요없이 인덱스 번호가 50인 요소를 만들 수 있다느 의미임   
// 이 배열에 자동 길이 변수가 있으면 그 길이 변수는 4가 아닌 51로 설정됨   
// 요소 번호를 지정할 때 건너뛰는 번호가 없는 배열을 만들 수 있지만 반드시 그렇게 해야 하는 것은 아님   
// 실제로 JScript에서는 배열의 아래 첨자에 번호를 지정하지 않아도 됨   
- JScript's array is flexible   
- This means that if there are three elements in an array and the index numbers are 0, 1, and 2, respectively, you can create elements with index numbers 50 without having to add elements from 3 to 49   
- If there is an auto-length variable in this array, the length variable is set to 51 instead of 4   
- When specifying element numbers, you can create an array without skipping numbers, but you do not have to do so   
- In fact, JScript does not need to number subscripts in an array   
   
// JScript에서는 개체와 배열이 본질적으로 서로 동일함   
// 실질적인 차이점은 데이터에 있는 것이 아니라 배열의 구성원 또는 개체의 속성과 메서드에 주소를 지정하는 방식이 있음   
- In JScript, objects and arrangements are essentially identical to each other   
- The real difference is not in the data, but the way you address the properties and methods of members or objects in the array   
   
<br />
### Specify Array Addresses   
// 배열 주소 지정   
   
// 배열 구성원의 주소를 지정하는 방식에는 크게 두 가지가 있음   
- There are two main ways to address an array member   
   
// 1. 대괄호를 사용하여 배열에 주소를 지정하는 방식   
// - 대괄호 안에는 숫자 값이나 음수가 아닌 정수를 산출하는 식을 입력할 수 있음   
// - 아래 예시는 entryNum 변수를 정의하고 스크립트의 다른 곳에서 그 값을 지정한 것을 전제로 하고 있음   
   
1 . How to address an array using brackets   
- In brackets, you can enter an expression that yields an integer that is not a number or a negative number   
- The example below presupposes that an entryNum variable is defined and that the value is specified elsewhere in the script   
   
```javascript
theListing = addressBook[entryNum];
theFirstLine = theListing[1];
```
   
// 이 방식은 개체의 주소를 지정하는 방식과 동일함   
// 단, 개체 주소를 지정할 때는 마침표 다음에 실제 속성 이름을 입력해야 함   
// 입력한 속성이 없을 경우 코드는 오류를 일으킴   
- This method is the same as addressing an object   
- However, when you specify an object address, you must enter the actual property name after the period   
- Code will fail if no properties are entered   
   
// 2. 번호가 지정되어 있는 속성을 가진 개체/배열을 만든 후 로프에서 그 번호를 생성하는 방식   
// - 아래 예시는 두 개의 배열을 생성함   
// - 하나는 이름용이고 다른 하나는 주소용으로 이것은 주소록의 목록을 이용함   
// - 각 배열에는 4가지 속성이 있음   
// - 예를 들어 theListing의 [Name1]에서 [Naem4]까지의 속성에 작성된 theName의 인스턴스는 "G.", "Edward", "Heatherington", "IV" 또는 "George", "Sand"를 포함할 수 있음   
   
2 . How to create an object/array with a numbered property and then generate that number from a rope   
- In the example below, two arrays are created   
- One for name and the other for address, which uses a list of address books   
- Each array has four properties   
- For example, an instance of theName created in a property from [Name1] to [Naem4] in theListing can include "G.", "Edward", "Heatherington", "IV" or "George", "Sand"   
   
```javascript
theListing = addressBook[entryNum];
for (i = 1; i < 4; i++) {
    theName[i] = theListing["Name" + i];
    theAddress[i] = theListing["Address" + i];
}
```
   
// 이런 특정한 인스턴스는 짧기 때문에 "점"을 사용하는 표기법으로 쓸 수 있음   
// 즉, theListing, theName, theAddress를 배열이 아닌 개체로 주소 지정을 할 수 있지만 이것이 항상 가능한 것은 아님   
// 때로는 런타임 때까지 특정 속성이 존재하지 않을 수도 있으며 특정 속성이 어떤 속성이 될 것인지를 미리 알 수 없기도 함   
// 예를 들어, addressBook 배열을 번호가 지정되어 있는 목록 대신에 성으로 정렬하면 스크립트를 실행하면서 사람을 찾기 위해 "진행 중에" 이름을 입력할 수 있음   
// 아래 예시는 스크립트 내의 어딘가에 적절한 함수 정의가 있다는 것을 전제함   
- Because these particular instances are short, they can be written in a notation that uses a "dot."   
- This means that you can address theListing, theName, and theAddress as objects rather than arrays, but this is not always possible   
- Sometimes a particular attribute may not exist until runtime and it is not known in advance what attribute a particular attribute will be   
- For example, if you sort an addressBook array by last name instead of a numbered list, you can type a name "in progress" to find people while running a script   
- The example below presupposes that there is an appropriate function definition somewhere in the script   
   
```javascript
theListing = addressBook[getName()];
theIndivListing = theListing[getFirstName()];
```
   
// 이것은 연상식 주소 지정임   
// 즉, 임의의 문자열을 사용하여 주소를 지정하는 것임   
// 실직적으로 JScript의 개체는 연상식 배열임   
// "점"을 사용하여 주소 지정을 할 수 있고, 또 그렇게 자주 지정하고 있음에도 불구하고 반드시 그 방식을 사용할 필요는 없음   
// 배열 표시로 JScript 개체의 구성원에 액세스할 수 있으므로 JScript 개체를 연상식 배열로 사용할 수 있음   
- This is an associated addressing   
- In other words, addressing using any string   
- Unemploymentally, JScript objects are associated arrays   
- "Dots" can be used to address, and even though they are specified so often, they are not necessarily required to use that method   
- You can use the JScript object as an associative array because the array display provides access to members of the JScript object   
   
// 아래 코드는 가장 많이 사용되는 형식의 배열을 만들고 초기화함   
- The code below creates and initializes the most commonly used array   
   
```javascript
var myArray = new Array("Athens", "Belgrade", "Cairo");
```
   
// 이 배열의 각 요소는 요소 번호를 사용하여 주소가 지정됨   
// 이 경우에는 0, 1, 2 임   
// 이 배열은 for...in 문을 사용하여 0에서 시작하여 2에서 끝나는 반복을 수행할 수 있음   
// 예를 들어 다음과 같음   
- Each element in this array is addressed using an element number   
- In this case, it's 0, 1, 2   
- This array can be repeated starting at 0 and ending at 2 using for...in statement   
- For Example   
   
```javascript
for (key in myArray)
    response.write("Element value is " + MyArray[key] + "<BR>");
```
   
// 아래 코드는 요소 3개를 포함하는 연상식 배열을 만들고 초기화함   
- The code below creates and initializes an associative array containing three elements   
   
```javascript
var MyArray = {
    "a" : "Athens", "b" : "Belgrade", "c" : "Cairo"
};
```
   
// 이 배열에서는 배열 요소 번호 (0, 1, 2) 대신 키 문자열 ("a", "b", "c") 을 사용하여 요소의 주소가 지정됨   
// 이것은 좀 더 직관적인 주소 지정 구성표를 지닌 배열을 만들어 사용할 수 있게 해줌   
// 위에서 예시한 for...in 문 코드 또한 이 배열을 반복 수행하는데 사용할 수 있음   
- In this array, elements are addressed using key strings ("a", "b", "c") instead of array element numbers (0, 1, 2)   
- This makes it possible to create and use arrays with more intuitive addressing schemes   
- The for...in statement code illustrated above can also be used to repeat this arrangement   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
