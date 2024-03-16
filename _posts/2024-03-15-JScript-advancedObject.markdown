---
layout: post
title:  "JScript: Advanced Object"
date:   2024-03-15 09:00:00 +0900
categories: [JScript]
---

### Create advanced objects   
// 고급 개체 작성   
   
### Creating Objects Using Constructors   
// 구성자를 사용하여 개체 작성   
   
// JScript에서는 구성자를 사용하여 개체 클래스를 만들 수 있음   
// new문으로 구성자를 불러오며, 구성자는 문이 구성하는 모든 것을 반환함   
- In JScript, object classes can be created using constructors   
- The constructor is imported into a new statement, and the constructor returns everything the statement comprises   
   
// 특별한 Function 구성자를 사용하면 익명의 함수를 만들 수 있음   
// 익명의 함수는 이름이 없는 함수임   
// 예를 들어, 다른 함수 내부에 있는 지시자의 하나로 Function 구성자를 사용하여 함수를 "진행 중에" 만들 수 있음   
// 이러한 함수는 한 위치에서만 사용되므로 이름이 필요 없음   
- Using special Function constructors, anonymous functions can be created   
- An anonymous function is an unnamed function   
- For example, a function can be created in progress using the Function constructor as one of the indicators inside another function   
- These functions are only used in one location, so no names are required   
   
// 아래 예시에서는 그러한 익명 함수가 "name-and-email-address" 목록을 한줄로 작성함   
// 익명 함수는 firstNameFirst 변수 값을 검사하여 성과 이름 중에서 어느 것을 처음에 쓸 것인지 결정하고, emailNameFirst 변수 값을 검사하여 전자 메일 주소와 이름 중에서 어느 것을 먼저 쓸 것인지 결정함   
// 이 예시에서는 firstNameFirst 값과 emailNameFirst 값이 이미 다른 곳에서 설정되었다고 가정함   
- In the example below, such an anonymous function creates a "name-and-email-address" list in a single line   
- The anonymous function checks the value of the firstNameFirst variable to determine which of the first name and the first name, and checks the value of the emailNameFirst variable to determine which of the email addresses and names to write first   
- This example assumes that the firstNameFirst and emailNameFirst values are already set elsewhere   
   
```javascript
for(j = 1; j < addressList[length]; j++)
{
    oneListingLine = new Function(
        emailNameFirst, 
        firstNameFirst, 
        addressList, 
        j, 
        theName = new Function(
            firstNameFirst, 
            addressList, 
            j, 
            var theName = (
                addressList[j].firstName + addressList[j].lastName
            );
            if(firstNameFirst) {
                theName = (addressList[j].firstName + addressList[j].lastName);
            }
            ,
        );

        if(emailNameFirst) {
            theListing = addressList[j].emailName + ":\t" + theName
        } else {
            theListing = theName + ":\t" + addressList[j].emailName; return theListing;
        }
    )
    document.write(oneListingLine + "<br>");
}
```
   
### Using Constructors   
// 구성자 쓰기   
   
// 구성자를 직접 쓰려면 구성자 내에서 this 키워드를 사용하여 새로 만들어진 개체를 참조해야 함   
// 구성자는 개체를 초기화 함   
- To use the constructor directly, you must refer to newly created objects using the this keyword within the constructor   
- Constructor initializes objects   
   
// 다음 예시에서 구성자는 인덱스를 0에서 지정하지만 반드시 0에서 시작할 필요는 없음   
// 예를 들어, 배열 인덱스나 개체 인덱스의 실제 번호를 가리키는 매개 변수를 원한다면 첫째 인덱스를 1로 지정할 수 있음   
// 이 예시에서는 내부 Array()개체의 자동 유지 길이 매개변수와 구별하기 위하여 이 매개변수를 extent라고 함   
// 배열에 속성을 추가하는 코드를 쓰고 있다면 extent 매개변수(또는 상당어구)를 업데이트 해야 함   
// 왜냐하면 JScript에서는 이러한 매개변수를 지원하지 않기 때문임   
// 이와 같이 매우 간단한 예시도 현재 개체를 참조하기 위하여 개체(점)와 배열(대괄호) 표시법을 사용함   
- In the following example, the constructor specifies an index from 0 but does not necessarily start at 0   
- For example, if you want a parameter that points to the actual number of an array index or object index, you can specify the first index as 1   
- In this example, this parameter is called extent to distinguish it from the auto-hold length parameter of the internal Array() object   
- If you are using code to add properties to an array, you need to update the extent parameter (or equivalent phrase)   
- Because JScript does not support these parameters   
- This very simple example also uses object (point) and array (bracket) representations to refer to the current object   
   
```javascript
function MakeStringArray(length)
{
    this.extent = length;
    for(iNum = 0; iNum < length; i++)
    {
        this[iNum] = "";
    }
}

// 구성자를 사용하여 배열을 만들고 초기화함
// - Create and initialize an array using a constructor
myStringArray = new MakeStringArray(63);
```
   
### Create an object using the initial settings   
// 초기 설정을 사용하여 개체 작성   
   
// 개체를 정의할 때 prototype 속성을 사용하면 정의에 의해 만들어지는 모든 개체에 공통으로 유효한 속성을 만들 수 있음   
// prototype 속성들은 참조용으로 클래스의 각 개체로 복사됨   
// 따라서 prototype 속성들은 클래스의 모든 개체에 대해 같은 값을 가짐   
// 그러나 사용자는 한 개체에서 prototype 속성 값을 변경할 수 있으며, 변경된 새로운 값은 기본값을 재정의함   
// 그러나 이러한 변경사항은 해당 인스턴스에만 적용되므로 클래스의 구성원인 다른 개체는 변경으로 인한 영향을 받지 않음   
- When you define an object, you can use prototype properties to create properties that are commonly valid for all objects created by the definition   
- Prototype properties are copied to each object in the class for reference   
- Therefore, prototype attributes have the same value for all objects in the class   
- However, users can change the prototype property value on one object, and the new value that has been changed overrides the default value   
- However, these changes only apply to that instance, so other objects that are members of the class are not affected by the changes   
   
// 이러한 원칙을 사용하면 JScript 언어의 일부분인 개체, 즉 초기 설정을 가지고 있는 모든 개체에 대한 속성을 추가로 정의할 수 있음   
// 예를 들어, 계산을 하기 위한 특별한 상수를 원하지만 Math개체와 Number 개체에서 그 상수가 제공되지 않을 경우, 사용자는 스스로 상수를 정의하여 각각의 개체 초기 설정 또는 개체 클래스의 초기 설정 속성에 할당할 수 있음   
- These principles allow you to further define properties for objects that are part of the JScript language, i.e. any object that has an initial setting   
- For example, if a user wants a special constant for making calculations, but the Math object and the Number object do not provide that constant, the user can define the constant himself and assign it to the initial setting properties of each object or object class   
   
```javascript
Math.prototype.Avogadro = 6.0232E23;
function howManyMolecules(wtGrams, molWt)
{
    return ((wtGrams/molWt) * Math.prototype.Avogadro);
}

document.write("There are " + howManyMolecules(window.prompt("How many grams?", 0), window.prompt("What's the molecular weight?", 0)) + " molecules in that amount.");
```
   
// 좀 더 구체적으로 설명하면, 사용자는 함수를 정의하여 해당 함수를 String.prototype에 메서드로 지정할 수 있으며, 스크립트의 어떤 문자열에도 함수를 사용할 수 있음   
- To be more specific, users can define a function and specify it as a method for String.prototype, functions can be used for any string in the script   
   
// 아래 예시에서는 스크립트의 다른 곳에서 정의된 "theElements"라는 주기율표 배열이 있다고 가정함   
// 물론 이러한 주기율표에는 원소기호, 원소이름, 원자량 및 기타 원소 관련 정보가 포함되어 있음   
- The example below assumes that there is an array of periodic tables called "theElements" defined elsewhere in the script   
- Of course, these periodic tables contain atom symbols, atom names, atomic weights, and other atom-related information   
   
```javascript
function atomName(theSymbol)
{
    return (theElements[theSymbol].fullName);
}

String.prototype.atomName = atomName;

function decodeFormula(theFormula)
{
    var theCurrentPiece = "";
    var theDecodedFormula = "";
    for(i = 1; i = theFormula.length; i++)
    {
        if(theFormtheCurrentPiece)
        // 수식 문자열을 기호와 숫자의 배열로 분리하는 코드문
        // - a code statement that separates an expression string into an array of symbols and numbers

        // 수식 배열을 통한 루프와 해독 문자열 조립
        // 각 항목은 다음과 같음
        // - Assembling loops and decryption strings with an array of formulas
        // - Each item is as follows
        theDecodedFormula += formula[n].number;
        theDecodedFormula += " ";
        theDecodedFormula += formula[n].symbole.prototype.atomName;
        theDecodedFormula += "";
    }

    return theDecodedFormula;
}
decodeFormula(window.prompt("formula?", "A1203"));
```
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
