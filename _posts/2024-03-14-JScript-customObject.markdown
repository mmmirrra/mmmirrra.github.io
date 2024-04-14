---
layout: post
title:  "JScript: Custom Object"
date:   2024-03-14 09:00:00 +0900
categories: [JScript]
---

### Create objects yourself   
// 개체 직접 만들기   
   
// 개체의 인스턴스를 만들려면 개체에 속성과 필요에 따라 메서드를 지정하여 개체를 정의해야 함   
- To create an instance of an object, you must define the object by specifying properties and methods as needed   
   
// 아래 예시에서는 pasta 개체를 정의함   
// this 키워드는 현재 개체를 지칭하기 위해 사용함   
- The example below defines a pasta object   
- This keyword is used to refer to the current object   
   
```jscript
function pasta(grain, grain2, width, shape, shapenum, extent, agg)
{
    // The number of attributes in the object. length is not included in the number of attributes.
    this.length = 7;
    // What kind of grain is the pasta made of? (String)
    this.grain = grain;
    // Does pasta have other grains? (String)
    this.grain2 = grain2;
    // What is the thickness of the pasta? (number)
    this.width = width;
    // What is the shape of the cross section? (String)
    this.shape = shape;
    // Is it one of the registered shapes of pasta? (number)
    this.shapenum = shapenum;
    // How long is the pasta? (number)
    this.extent = extent;
    // Is there egg in the pasta dough? (boolean)
    this.egg = egg;
}
```
   
// 일단 개체를 정의하면 new 연산자를 사용하여 개체의 인스턴스를 만듦   
- Once you have defined an object, use the new operator to create an instance of the object   
   
```jscript
var spaghetti = new pasta("wheat", "", 0.2, "circle", 9, 30, true);
var linguine = new pasta("wheat", "", 0.3, "oval", 17, 30, true);
```
   
// 개체의 한 인스턴스에 속성을 추가하면 해당 인스턴스를 변경할 수 있음   
// 그러나 이러한 속성은 개체 정의의 일부분이 될 수 없으며 속성을 특별히 추가하지 않는 한 다른 인스턴스에는 이러한 속성이 나타나지 않음   
// 개체의 모든 인스턴스에 추가 속성이 나타나도록 하려면 이들 속성을 개체 정의에 추가해야 함   
- Adding properties to an instance of an object allows you to change that instance   
- However, these properties cannot be part of the object definition, and they do not appear in other instances unless you specifically add them   
- To ensure that additional properties appear on all instances of an object, you must add them to the object definition   
   
```jscript
// Additional Properties for Spaghetti
spaghetti.color = "a light straw color";
spaghetti.drycook = 7;
spaghetti.freshcook = 0.5;

var showFun = new pasta("rice", "", 3, "basic", , 12, false);
/*
    The chaowFum object, linguine object, and paste object definition do not have three additional properties specified in the spaghetti object
*/
```
   
<br />
### Include methods in definition   
// 정의에 메서드 포함하기   
   
// 메서드를 개체 정의에 포함시킬 수 있음   
- Method can be included in object definition   
   
// 아래 예시에서는 문자열 배열과 메서드로 구성된 개체를 만듦   
// 메서드는 문자열을 배열에 추가시키는데, 이 때 크기를 증가시킴   
// 이렇게하면 개체의 인스턴스를 무한대로 확장시킬 수 있음   
- The example below creates an object consisting of string arrangements and methods   
- The method adds a string to the array, increasing its size   
- This allows the instance of an object to be expanded to infinity   
   
```jscript
// 목록을 확장시킬 함수를 정의함
// - Define a function to expand the list
function addItem(newItem)
{
    // 배열의 길이를 늘림
    // - Increase the length of the array
    this.length += 1;
    // 새 항목을 추가하고 항목에 번호를 매김
    // - Add new items and number them
    this[(this.length - 1)] = newItem;
}

// "shopping list" 개체를 정의
// - Define the "shopping list" object
function shoppingList(firstItem)
{
    // 개체의 속성 수. length는 속성 수에 포함되지 않음
    // - The number of attributes in the object. length is not included in the number of attributes
    this.length = 2;
    // 메서드로 addItem 함수를 포함
    // - Include the addItem function as a method
    this.addItem = addItem;
    // 첫째 항목은 1
    // - The first item is 1
    this[(this.length - 1)] = firstItem;
}

var myList = new shoppingList("milk");
// 메서드를 사용하여 달걀을 추가하고 이것은 항목 2가 됨
// - Use the method to add an egg and this becomes Item 2
myList.addItem("egg");
// 빵은 항목 3이 됨
// - The bread will be item 3
myList.addItem("bread");
```
   
// 여기서 배열의 내용은 다음과 같음   
// - myList[length]는 4임   
// - myList[addItem]는 addItem 함수임   
// - myList[1]는 milk임   
// - myList[2]는 egg임   
// - myList[3]은 bread임   
- Here, the contents of the array are as follows   
  - myList[length] is 4   
  - myList[addItem] is addItem function   
  - myList[1] is milk   
  - myList[2] is egg   
  - myList[3] is bread   
   
// 인덱스는 엄격하게 숫자 방식으로 처리된다 하더라도 기대만큼 정확하지 않음   
// 이 배열에 for...in 루프를 실행하면 루프는 여기에 주어진 순서대로 반복하고 루프 변수는 초기 값으로 0이 아니라 "length"를 가지게 됨   
- Indexes are not as accurate as expected, even if they are handled strictly numerically   
- Running a 'for...in' loop on this array will repeat the loop in the order given here and the loop variable will have "length" instead of 0 as its initial value   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
