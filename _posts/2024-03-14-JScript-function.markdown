---
layout: post
title:  "JScript: Function"
date:   2024-03-14 09:00:00 +0900
categories: [JScript]
---

### Overview of functions   
// 함수개요   
   
// Microsoft JScript 함수는 동작을 수행함   
// 또한 함수는 결과를 반환하기도 함   
// 때때로 함수는 연산이나 비교의 결과임   
- The Microsoft JScript function performs operation   
- Functions also return results   
- Sometimes a function is the result of an operation or comparison   
   
// 함수는 하나의 이름으로 여러개의 연산을 결합시킴   
// 이렇게 하면 코드를 단정하게 정리할 수 있음   
// 일련의 문을 쓸 수도 있고, 함수에 이름을 지정할 수도 있으며, 원할때마다 함수를 호출하여 함수에 필요한 정보를 함수에 전달함으로써 전체 집합을 실행할 수 있음   
- A function combines multiple operations with a single name   
- This will help you organize your code neatly   
- A function can write a series of statements, or name a function. A function can execute a whole set by calling another function whenever it wants and passing the information it needs to the function   
    
// 함수에 정보를 전달하려면 함수 이름 뒤에 나오는 괄호 안에 정보를 넣으면 됨   
// 함수로 전달되는 정보들은 인수 또는 매개 변수라고 함   
// 어떤 함수는 인수를 전혀 사용하지 않고, 어떤 함수는 인수를 한 개 사용하며, 어떤 함수는 인수를 여러 개 사용함   
// 함수 중에는 함수를 사용하는 방법에 따라 사용하는 인수의 수가 달라지는 함수도 있음   
- To pass information to a function, put it in parentheses after the function name   
- The information passed as a function is called an argument or parameter   
- Some functions use no arguments at all, some use one argument, and some use multiple arguments   
- Some functions have different numbers of arguments depending on how they are used   
   
// JScript는 두 종류의 함수를 지원함   
// 즉, 언어에 기본적으로 제공되는 함수와 사용자가 스스로 만드는 함수를 지원함   
- JScript supports two types of functions   
- In other words, it supports the functions that are built into the language and the functions that users create themselves   
   
<br />
### Special built-in functions   
// 특수 기본 제공 함수   
   
// JScript 언어에는 여러 개의 기본 제공 함수가 포함되어 있음   
// 사용자는 기본 제공 함수의 일부를 사용하여 식과 특수 문자를 처리할 수 있으며, 문자열을 숫자 값으로 변환할 수도 있음   
- The JScript language contains multiple built-in functions   
- Users can process expressions and special characters using some of the built-in functions, and can also convert strings into numerical values   
   
// 예를 들어 escape() 함수와 unescape() 함수는 HTML 코드에서 특수한 의미를 지니는 문자, 즉 직접 텍스트로 입력할 수 없는 문자를 변환하는 데 사용됨   
// "<"와 ">" 꺽쇠 괄호는 HTML 태그를 표시함   
- For example, the escape() and unescape() functions are used in HTML code to transform characters that have special meanings, i.e., characters that cannot be entered directly into text   
- "<" and ">" key brackets display HTML tags   
   
// escape 함수는 모든 특수 문자를 인수로 사용하며, 해당 특수 문자에 대한 제어 코드를 반환함   
// 각각의 제어 코드는 백분율 기호(%)와 그 뒤에 오는 두 자릿수로 구성됨   
- The escape function takes all special characters as arguments and returns a control code for that special character   
- Each control code consists of a percentage symbol (%) followed by a double digit   
   
// unescape 함수는 escape 함수와 정반대임   
// 이 함수는 백분율 기호와 두 자리수로 구성된 문자열을 인수로 사용하여 문자를 반환함   
- Unescape function is the opposite of escape function   
- This function returns a character using a string of two digits with a percentage symbol as an argument   
   
// JScript가 기본적으로 제공하는 또 다른 유용한 함수로는 eval() 함수 들 수 있음   
// 이 함수는 문자열 형식으로 사용되는 모든 유효한 수학식을 계산함   
// eval() 함수는 인수를 한 개 사용하며 그 인수는 계산할 식임   
- Another useful function that JScript provides by default is the eval() function   
- This function calculates all valid mathematical expressions used in string format   
- The eval() function uses one argument and that argument is the expression to be calculated   
   
```javascript
var anExpression = "6 * 9 %7";

// Specify a value of 5 for the total variable
var total = eval(anExpression);
var yetAnotherExpression = "6 * (9 % 7)";

// Specify a value of 12 for the total variable
total eval(yetAnotherExpression);

// An error occurs
var totality = eval("It's surrounded by a lot of clams...");
```
   
<br />
### Create your own function   
// 함수 직접 만들기   
   
// 자기만의 함수를 만들어 필요할 때마다 사용할 수 있음   
// 함수 정의는 함수문과 JScript문 블록으로 구성됨   
- Create your own function and use it whenever you need it   
- Function definitions consist of function statements and JScript statements blocks   
   
// 아래 예시에 나오는 checkTriplet 함수는 삼각형의 세 변의 길이를 인수로 사용하고, 세 숫자가 피타코라스 정리(직각 삼각형의 빗변을 제공한 값은 다른 두 변의 제곱을 합한 값과 같음)를 구성하는지를 확인하여 삼각형이 직각 삼각형인지를 계산함   
// checkTriplet 함수는 두 개의 다른 함수 중 하나를 호출하여 실직적인 테스트를 함   
- The checkTriplet function in the example below uses the lengths of the three sides of a triangle as an argument and determines whether the three numbers comprise the Pythakoras Theorem (The value that provides the hypotenuse of a right triangle is equal to the sum of the squares of the other two sides) to determine if the triangle is a right triangle   
- The checkTriplet function calls one of two different functions to perform an unemployment test   
   
// 부동 소수점 테스트에서 테스트 변수로 아주 작은 숫자("앱실론")를 사용함   
// 부동 소수점 계산의 불확실성 오류와 반올림 오류 때문에 논의되고 있는 세 값이 정수가 아니면 빗변을 제곱한 값이 다른 두 변의 제곱을 합한 값과 같은지를 직접 테스트한다는 것은 혅실적이지 못함   
// 직접적인 테스트가 더 정확하므로, 아래 예제의 코드는 정수가 적절한지를 결정하고, 만일 정수가 적절하다면 그것을 사용함   
- Floating point tests use very small numbers ("epsilon") as test variables   
- Because of the uncertainty and rounding errors in floating point calculations, it is not practical to directly test whether the squared value of the hypotenuse is equal to the sum of the squares of the other two sides if the three values being discussed are not integers   
- Since the direct test is more accurate, the code in the example below determines whether an integer is appropriate and uses it if it is appropriate   
   
```javascript
var epsilon = 0.0000000000001;  // Very small number to test
var triplet = false;

// 정수 테스트 함수
// - integer test function
function integerCheck(a, b, c)
{
    if((a*a) == ((b*b) + (c*c)))
    {
        triplet = true;
    }
}

// 부동 소수점 숫자 테스트 함수
// - Floating point number test function
function floatCheck(a, b, c)
{
    // 테스트 숫자를 만듦
    // - Create test numbers
    var theCheck = ((a*a) - ((b*b) + (c*c)))

    // 테스트에는 절대값이 필요하므로, 음수일 경우에는 theCheck를 양수로 만듦
    // - The test requires an absolute value, so if it is negative, make the theCheck positive
    if(theCheck < 0)
    {
        theCheck *= -1;
    }
    
    // theCheck가 앱실론에 가깝다면 매우 가까움
    // - If theCheck is close to epsilon, it's very close
    if(epsilon > theCheck)
    {
        triplet = true;
    }
}

// triplet 검사 함수. 먼저 가장 긴 변을 "a" 위치로 옮김
// - triplet check function, first move the longest side to the "a" position
function checkTriplet(a, b, c)
{
    // 임시 저장소를 만듦
    // - Create a temporary repository
    var d = 0;

    // c > b 이면 교환
    // - If it's "c > b", exchange it
    if(c > b)
    {
        d = c;
        c = b;
        b = d;
    }
    // 아니면 무시
    // - Or ignore it

    // b > a 이면 교환
    // - If it's "b > a", exchange it
    if(b > a)
    {
        d = b;
        b = a;
        a = d;
    }
    // 아니면 무시
    // - Or ignore it

    // 한 변이 있을 경우 "a" 변은 이제 빗변임
    // 세 값을 모두 테스트함. 모두 정수?
    // - If there is one side, the "a" side is now an oblique side
    // - Tested all three values. All integers?
    if(((a % 1) == 0) && ((b % 1) == 0) && ((c % 1) == 0))
    {
        // 정수라면 정밀한 검사를 사용함
        // - If it is an integer, use a precise check
        integerCheck(a, b, c);
    }
    else 
        // 아니면 합리적으로 가능한 근사치를 가져옴
        // - Or get a reasonably possible approximation
        floatCheck(a, b, c);
}

// 아래의 세 문은 테스트용으로 예시 값을 지정
// - The following three statements specify example values for testing
var sideA = 5;
var sideB = 5;
var sideC = Math.sqrt(50);

// 함수 호출. 호출 후에 triplet에는 결과가 포함됨
// - a functional call. triplet contain results after call
checkTriplet(sideA, sideB, sideC);
```
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
