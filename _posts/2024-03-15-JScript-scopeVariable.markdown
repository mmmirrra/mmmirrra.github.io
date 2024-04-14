---
layout: post
title:  "JScript: Scope of Variable"
date:   2024-03-15 09:00:00 +0900
categories: [JScript]
---

// 두 가지 범위, 즉 전역과 지역이 있음   
// 함수 정의의 외부에 변수를 선언하면 전역 변수가 되고, 그 값은 프로그램 전체에서 엑세스하거나 수정할 수 있음   
// 함수 정의의 내부에 변수를 정의하면 이 변수는 지역 변수가 됨   
- There are two ranges : global and local   
- Declaring a variable outside a function definition becomes a global variable, and its value can be accessed or modified throughout the program   
- Variables defined inside the function definition become local variables   
   
// 지역 변수는 전역 변수와 동일한 이름을 가질 수 있지만, 지역 변수는 전역 변수와 완전하게 구별되며 별개의 것임   
// 결론적으로 말해 한 변수의 값을 변경해도 다른 변수에 영향을 미치지 않음   
// 지역 변수가 정의된 함수 내부에는 오직 지역 변수만이 의미를 가짐   
- Local variables can have the same name as global variables, but local variables are completely distinct from global variables   
- In conclusion, changing the value of one variable does not affect the other variable   
- Only the local variable has meaning inside the function where the local variable is defined   
   
```javascript
// Global definition of aCentaur
var aCentaur = "a horse on which a rider is riding";

// Local aCentaur variable is declared in this function
function antiquities()
{
    var aCentaur = "Kentauros would be a skitai warrior on horseback";
    // Add to a local variable
    aCentaur += ", It is incorrectly reported as follows";
}

var nothinginparticular = antiquities();
aCentaur += ", Like you're naively watching from afar";

/*
    // The variable inside the function contains "Kentauros would be a skitai warrior on horseback, It is incorrectly reported as follows"
    // Variables outside the function contain the remaining statement "a horse on which a rider is riding, Like you're naively watching from afar".
*/
```
   
// 변수는 변수가 존재하는 범위가 무엇이든 그 범위의 시작 부분에서 선언된 것처럼 동작함   
// 그 결과 가끔씩 예상치 못한 동작을 함   
- Variables behave as if they were declared at the beginning of the range, whatever the range in which the variable exists   
- As a result, sometimes unexpected behavior   
   
```javascript
var aNumber = 100;
var withAdditive = 0;

withAdditive += aNumber;    // withAdditive is currently 100
tweak();
withAdditive += aNumber;    // withAdditive is currently 200

function treak()
{
    // Explicit declaration of newThing variable
    var newThing = 0;
    
    // If there is no comment, the following statement will cause an error
    // newThing = aNumber;

    // The following statement specifies the value of 42 for the aNumber region variable, implicitly declaring the aNumber region variable
    aNumber = 42;

    if (false){
        var aNumber;    // This statement does not run
        aNumber = "Hello!";  // This statement does not run
    }
}
```
   
// 주석이 있는 이 문은 지역 변수 aNumber의 값을 지역 변수 newThing에 지정하려고 함   
// 이런 경우 지역 변수 aNumber가 함수의 다른 곳에서 정의되어 전체에 존재함에도 불구하고 실패함   
// aNumber 변수는 이 문이 코드에서 발생하는 시점에서 어떤 값도 지정받지 못하여 undefined가 됨   
- This statement with annotations attempts to specify the value of the local variable aNumber in the local variable newThing   
- In this case, the local variable aNumber failed even though it was defined elsewhere in the function and existed throughout   
- The aNumber variable is undefined because no value is specified at the time this statement occurs in the code   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
