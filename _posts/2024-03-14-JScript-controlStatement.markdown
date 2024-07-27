---
layout: post
title:  "JScript: Conditional Statement - Control Structure - if / for / while / break / continue"
date:   2024-03-14 09:00:00 +0900
categories: [JScript]
---

### Why Control the Run Flow   
// 실행 흐름을 제어하는 이유  
   
// 조건이 다르면 다른 작업을 수행하는 스크립트가 필요한 경우가 많이 있음   
// 예를 들어 매시간마다 시간을 확인하고 그 날의 일정동안 적절하게 일부 매개 변수를 변경하는 스크립트가 필요할 수도 있을 것이며, 모종의 입력을 받아들여 그에 맞게 작동할 수 있는 스크립트가 필요할 수도 있음. 또는 지정한 동작을 반복하는 스크립트가 필요할 수도 있음   
- Different conditions often require scripts to perform different tasks   
- For example, the code may require a script that checks the time every hour and changes some parameters appropriately throughout the day's schedule, may require a script that can accept some input and work accordingly, or may require a script that repeats a specified action   
   
// 사용자들이 테스트할 수 있는 여러 종류의 조건들이 있음   
// microsoft JScript에서 할 수 있는 모든 조건 테스트는 Boolean임   
// 따라서 모든 테스트의 결과는 true 이거나 false임   
// 사용자는 Boolean, Number 또는 String 형식의 값들을 자유롭게 테스트할 수 있음   
- There are many types of conditions that users can test   
- All conditions tests available in Microsoft JScript are Boolean   
- Therefore, the result of all tests is true or false   
- Users are free to test values in Boolean, Number or String format   
   
// JScript는 다양한 가능성을 지닌 제어 구조를 제공함   
// 가장 간단한 제어 구조는 조건문임   
- JScript provides a control structure with a variety of possibilities   
- The simplest control structure is the conditional statement   
   
<br />
### Using Conditional Statements   
// 조건문 사용   
   
// JScript는 if 조건문과 if...else 조건문을 지원함   
// if문에서는 한 조건이 테스트되고 해당 조건이 테스트를 만족시키면 사용자가 만든 JScript 코드가 실행됨   
- JScript supports if conditional statements and if...else conditional statements   
- The if statement executes the user-created JScript code when a condition is tested and that condition satisfies the test   
   
// if...else 문에서는 조건이 테스트를 만족시키지 못하면 다른 코드가 실행됨   
- If...else statement will run another code if the condition does not satisfy the test   
   
// 가장 간단한 형태의 if문은 한줄로도 완벽하게 쓸 수 있지만 여러 줄로 된 if문과 if...else문이 훨씬 더 일반적임   
- The simplest form of if statement can be written perfectly in a single line, but multiple lines of if statement and if...else statement are much more common   
   
// 예시   
// - if문과 if...else문에서 사용할 수 있는 구문을 보여주고 있음   
// - 첫번째 예시는 가장 간단한 Boolean 테스트를 보여줌   
// - 괄호 안의 항목이 true이면, if 뒤의 문이나 문 블록이 실행됨   
- Example   
  - Show sentence available for if statement and if...else statement   
  - The first example shows the simplest Boolean test   
  - If the entry in parentheses is true, the statement or statement block after if is executed   
   
```javascript
// smash() 함수는 코드의 다른 곳에 정의되어 있음
// - The smash() function is defined elsewhere in the code
if (newShip)
    // newShip가 true인지 여부를 가리는 Boolean 테스트
    // - Boolean test to determine if newShip is true
    smash(champagneBottle, bow);

// 이 예시에서는 두 조건이 모두 true가 아니면 테스트는 실패
// - In this example, if both conditions are not true, the test fails
if (rind.color == "deep yellow" && rind.texture == "creases large and small") {
    theResponse = ("Is this Crenshaw melon? <br>");
}

// 이 예시에서는 두 조건 중 하나만 true이어도 테스트는 성공
// - In this example, the test is successful even if only one of the two conditions is true
var theReaction = "";
if ((lbsWeight > 15) || (lbsWeight > 45)) {
    theReaction = ("Oh, cute kitten! <br>");
} else
    theReaction = ("The cat there is big! <br>");
```
   
<br />
### Condition Operator   
// 조건 연산자   
   
// JScript는 또한 함축적인 조건 형식을 지원함   
// JScript에서는 조건 앞에 if라는 단어를 사용하지 않고 테스트할 조건 뒤에 물음표를 사용하고, 두 개의 대안을 지정하는데, 하나는 조건이 만족될 경우에 사용될 대안이고 다른 하나는 조건이 만족되지 못할 경우에 사용될 대안임   
// 두 대안은 콜론으로 구분됨   
- JScript also supports implicit conditional formats   
- JScript does not use the word 'if' before the condition, but a question mark after the condition to be tested. Two alternatives are specified, one to be used if the condition is satisfied and the other to be used if the condition is not satisfied   
- The two alternatives are separated by colon   
   
```javascript
var hours = "";
// 시간이 theHour 또는 theHour - 12 의 의미를 포함한다는 것을 나타내는 코드
// - Code indicating that time contains the meaning of theHour or theHour - 12
hours += (theHour >= 12) ? " 오후" : " 오전";
```
   
#### Tip   
   
// 여러 개의 조건을 함께 테스트해야 하고 테스트가 OR (\|\|) 로 연결되는지 또는 AND (&&) 로 연결되는지에 따라 한 조건이 다른 나머지 조건보다 실패 또는 성공할 가능성이 높다는 것을 알고 있는 경우, 해당 조건을 조건문의 처음에 두면 스크립트 실행 속도가 빨라질 수 있음   
- If you need to test multiple conditions together, and you know that one condition is more likely to fail or succeed than the other, depending on whether the test is connected to OR (\|\|) or AND (&&), you can speed up script run if you put that condition expression at the beginning of the condition statement   
   
// 예를 들어, 3가지 조건이 모두 true이어야 할 경우 (&& 연산자 사용) 두번째 테스트에 실패하면 세번째 조건은 테스트되지 않음   
// 이와 유사하게 여러 조건 중에 한 조건이 true 이어야 할 경우 (\|\| 연산자 사용), 어느 하나의 조건이 테스트를 통과하게 되면 테스트는 멈추게 됨   
// 이것은 테스트할 조건에 함수 호출 또는 다른 코드의 실행을 포함하고 있을 경우에 특히 효과적임   
- For example, if all three conditions must be true (using && operators), if the second test fails, the third condition is not tested   
- Similarly, if one of the conditions has to be true (using \|\| operators), the test will stop if either condition passes the test   
- This is particularly effective if the conditions to be tested include function calls or the run of other codes   
   
// 짧은 길이로 문을 구성하는데 따른 부작용은 아래 예제에서 runfirst()가 0 또는 false를 반환하면 runsecond가 실행되지 않는다는 것임   
-  A side effect of constructing a statement with a short length is that runsecond will not run if runfirst() returns 0 or false in the example below   
   
```javascript
if ((runfirst() == 0) || (runsecond() == 0)) {
    code...
}
```
   
<br />
### Repeat enable or loop   
// 반복 사용 또는 루프   
   
// 문이나 문 블록을 반복 실행하는 데는 몇 가지 방법이 있음   
// 일반적으로 반복적인 실행을 루핑이라고 함   
// 루핑은 전형적으로 몇가지 변수의 테스트에 의해 제어되는데, 변수의 값은 루프가 실행될 때마다 달라짐   
// Microsoft JScript는 for 루프, for...in 루프, while 루프, do...while 루프, switch 루프와 같은 다양한 종류의 루프를 지원함   
- There are several ways to run a statement or statement block repeatedly   
- Repetitive runs are typically referred to as looping   
- Looping is typically controlled by testing of several variables, whose values vary with each loop being executed   
- Microsoft JScript supports many types of loops, such as for loop, for...in loop, while loop, do...while loop, switch loop   
   
<br />
### Use for loop   
// for 루프 사용   
   
// for문은 카운터 변수, 테스트 조건 및 카운터를 업데이트하는 동작을 지정함   
// 매번 루프가 실행되기 직전에 (이것을 한 주기 또는 루프 일회 반복이라고 함) 조건이 테스트됨   
// 루프가 실행된 후 카운터 변수는 다음 반복이 시작되기 전에 업데이트 됨   
// 루핑 조건이 단 한 번도 만족되지 않으면 루프는 전혀 실행되지 않음   
// 테스트 조건이 항상 만족되면 무한 루프가 발생됨   
// 루프가 전혀 실행되지 않는 경우가 일부 바람직하지만 무한 루프가 발생하는 경우는 바람직하지 않으므로 루프 조건을 만들 때 주의해야 함   
- For statement specifies counter variables, test conditions, and actions to update counters   
- The condition is tested immediately before each loop is executed (This is called a cycle or loop iteration)   
- After the loop is executed, the counter variable is updated before the next iteration begins   
- If the looping condition is not met once, the loop will not run at all   
- An infinite loop occurs when the test conditions are always satisfied   
- Care should be taken when creating a loop condition, as it is partially desirable if no loop is running at all, but not if infinite loop occurs   
   
```javascript
/*
    // 업데이트 식 (아래 예제의 "icount++") 은 루프의 끝에서 실행되는데, 루프의 본문을 형성하는 문 블록이 실행된 후 조건이 테스트되기 전에 실행됨
    - The update expression ("icount++" in the example below) runs at the end of the loop. The update expression runs after the statement block that forms the body of the loop is executed before the condition is tested
*/

// 루프의 반복 횟수를 11로 제한
// - Limit the loop to 11 repetitions
var howFar = 11;

// 11개의 구성원 (0부터 10까지) 을 가진 sum이라는 배열을 만듦
// - Create an array called sum with 11 members (from 0 to 10)
var sum = new Array(howFar);
var theSum = 0;
sum[0] = 0;

// 이 경우 1부터 10까지 셈
// - In this case, count from 1 to 10
for (var icount = 1; icount < howFar; icount++) {
    theSum += icount;
    sum[icount] = theSum;
}

var newSum = 0;
// 전혀 실행되지 않음
// - It doesn't run at all
for (var icount = 1; icount > howFar; icount++) {
    newSum += icount;
}

var sum = 0;
// 무한 루프
// - It's an infinite loop
for (var icount = 1; icount > 0; icount++) {
    sum += icount;
}
```
   
<br />
### Use for...in Loop   
// for...in 루프 사용   
   
// JScript는 개체의 모든 속성을 통하여 단계적으로 작업할 수 있는 특별한 종류의 루프를 제공함   
// for...in 루프의 루프 카운터는 배열의 모든 인덱스를 단계적으로 작업함   
// 이것은 숫자가 아니라 문자열임   
- JScript provides a special kind of loop that allows you to work step by step across all the properties of an object   
- Loop counters in for...in loop work stepwise on all indexes in array   
- This is a string, not a number   
   
```javascript
// tagliatelleVerde 는 몇 가지 속성을 가진 개체임
// - A tagliatelleVerde is an object with several attributes
for (j in tagliatelleVerde) {
    // Various JScript code statements
}
```
   
<br />
### Use while loop   
// while 루프 사용   
   
// while 루프는 for 루프와 매우 유사함   
// 두 루프의 차이점이라면 while 루프에는 내부 카운터 변수나 업데이트 식이 없다는 것임   
// 이미 변수에 지정된 값에 반영되는 몇 가지 변경 조건이 있고, 그 조건을 이용하여 문이나 문 블록의 반복 실행을 제어하려면 while 루프를 사용함   
- The while loop is very similar to the for loop   
- The difference between the two loops is that the while loop has no internal counter variable or update expression   
- There are already several change conditions that are reflected in the value specified in the variable and use the while loop to control the repetitive running of a statement or statement block   
   
```javascript
var theMoments = "";

// Initializes the counter variable
var theCount = 42;

while (theCount >= 1) {
    if (theCount > 1) {
        theMoments = theCount + " element" + " is left";
    } else {
        theMoments = "One element is left";
    }

    // Updates the counter variables
    theCount--;
}
theMoments = "BLASTOFF!";
```
   
// while 루프가 명시적인 내부 카운터 변수를 가지지 않기 때문에 다른 루프 형식보다 무한 루프에 빠지기 쉬움   
// 게다가 루프 조건이 언제 어디에서 업데이트되는지를 알아내는 것이 쉽다고만 볼 수는 없으므로 조건이 업데이트 되지 않는 while 루프를 작성하기 쉬움   
// 따라서 while 루프를 설계할 때는 상당한 주의를 기울여야 함   
- It is easier to fall into infinite loops than other loop types because while loops do not have explicit internal counter variables   
- Moreover, it is not easy to find out when and where the loop condition is updated, so it is easy to create while loops where the condition is not updated   
- Therefore, considerable care must be taken when designing while loops   
   
<br />
### Use break and continue statements   
// break문과 continue문 사용   
   
// Microsoft JScript는 루프의 실행을 중단하는 문을 제공함   
- Microsoft JScript provides statements to stop the run of the loop   
   
// break문은 아마도 어떤 특별한 조건이 만족될 때 실행을 멈추기 위하여 사용됨   
- break statements are probably used to stop run when certain special conditions are met   
   
// continue문은 다음 반복 계산으로 즉시 이동하는데 사용되며, 코드 블록의 나머지 부분은 건너뛰지만 for 루프 또는 for...in 루프처럼 카운터 변수는 업데이트됨   
- The continue statement is used to move immediately to the next iterative calculation. Skip the rest of the code block but the counter variable is updated, such as for loop or for...in loop   
   
```javascript
var theComment = "";
var theRemainder = 0;
var theEscape = 3;
var checkMe = 27;
for (kcount = 1; kcount <= 10; kcount++) {
    theRemainder = checkMe % kcount;
    if (theRemainder == theEscape) {
        // 나머지가 중지값과 같은 값이 처음 나오면 루프를 빠져 나감
        // - If the remainder first comes up with the same value as the stop value, it exits the loop
        break;
    }
    theComment = "The remainder of " + checkMe + " /(divide) " + kcount + "is " + theRemainder + ".";
}

for (kcount = 1; kcount <= 10; kcount++) {
    theRemainder = checkMe % kcount;
    if (theRemainder != theEscape) {
        // 나머지와 중지값이 동일한 경우만을 선택하고 다른 경우는 모두 무시
        // - Select only if the rest and stop values are the same, and ignore all other cases.
        continue;
    }
    // 선택한 나머지를 사용하는 JScript 코드
    // - JScript code using the remaining selected
}

var theMoments = "";
// 카운터 초기화
// - The counter is initialized
var theCount = 42;
while (theCount >= 1) {
    if (theCount < 10) {
        // Warning!
        // Fell into an infinite loop using continue as follows
        // continue;
        // }
        if (theCount > 1) {
            theMoments = "There's " + theCount + "left!";
        } else {
            theMoments = "There's only one left!";
        }
        // 카운터 업데이트
        // - The counter will be updated
        theCount--;
    }
    theCount = "BLASTOFF!";
}
```
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
