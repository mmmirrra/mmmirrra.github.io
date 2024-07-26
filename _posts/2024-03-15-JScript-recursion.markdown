---
layout: post
title:  "JScript: Recursion"
date:   2024-03-15 09:00:00 +0900
categories: [JScript]
---

// 재귀는 중요한 프로그래밍 테크닉으로서 이것을 사용하여 함수 자체 내에서 그 함수를 다시 호출함   
// 쉬운 예시는 팩토리얼 (계승) 의 계산임   
// 0과 1의 계승은 특별히 1로 정의되어 있음   
// 그 이상의 수에 대한 계승은 1 * 2 * .. 와 같은 식으로, 계산하려는 숫자에 도달할 때까지 1씩 증가시켜서 곱함   
- Recursion is an important programming technique that uses this to recall the function within the function itself   
- An easy example is the calculation of a factorial   
- The factorial of 0 and 1 is specifically defined as 1   
- The factorial of any number above is multiplied by one until the number to be calculated is reached, such as '1 * 2 * ..'   
   
<br />
### Feature Description for Factorial Calculation   
// 계승 계산에 대한 기능 설명   
   
// "수가 0보다 작으면 계산을 거부하고, 정수가 아니면 소수점 이하를 버린 후의 정수를 사용함. 계승 수가 0 또는 1이면 그 계승값은 1이고, 1보다 크면 그것보다 1 작은 수가 될 때까지 계승값을 곱함"   
- "If the number is less than 0, reject the calculation, and if it is not an integer, use the integer after discarding the decimal point. If the factorial number is 0 or 1, the factorial value is 1, and if it is greater than 1, it is multiplied by the factorial value until it is 1 less."   
   
// 1보다 큰 수의 계승을 계산하려면 최소한 하나의 다른 수에 대한 계승값을 구해야 함   
// 그 계산을 하기 위해 사용하려고 하는 함수는 현재 사용하고 있는 바로 그 함수임   
// 따라서 현재 수를 실행하기 전에 먼저 자신을 호출해서 바로 이전의 작은 수에 대한 계산을 해야 함   
// 이것이 재귀의 한 예시임   
- To calculate a number of successors greater than 1, you must obtain a factorial value for at least one other number   
- The function we're trying to use to do that calculation is the one we're using right now   
- Therefore, the function must first call the self function before executing the current number and perform the calculation of the previous small number   
- This is an example of a recursion   
   
// 물론 곤경에 처할 수도 있음   
// 최종 결과값을 구하지도 못하고 종료지점에 이르지도 못하는 재귀 함수를 아주 쉽게 만들 수 있음   
// 이러한 재귀 함수는 컴퓨터로 하여금 소위 "무한" 루프라는 것을 실행하도록 만듦   
// 예를 들어, 계승 계산 설명에 있는 첫번째 규칙 (음수 처리 방법) 을 무시하고 임의 음수에 대한 계승 계산을 시도해 봅시다. 그러면 실패하게 되는데 그 이유는 예를 들어 -24의 계승을 계산하려면 그 전에 -25에 대한 것을 계산해야 하지만 또 그것을 계산하려면 마찬가지로 그 전에 -26에 대한 것을 계산해야 함. 따라서 이것은 영원히 종료지점에 이르지 못하게 됨   
- Of course, this could be in trouble   
- Makes it very easy to create recursive functions that do not obtain final results and do not reach termination points   
- These recursive functions cause the computer to execute what is called an "infinite" loop   
- For example, let's ignore the first rule (negative processing method) in the description of the factorial calculation and try the factorial calculation for arbitrary negative numbers. Then you fail because, for example, if you want to calculate the factorial of -24, you have to calculate the one for -25 before that, but you have to calculate the one for -26 before that. So it's not going to end forever   
   
// 그러므로 재귀 함수를 만들 때는 매우 신중히 설계하는 것이 무엇보다도 중요함   
// 만일 무한 재귀의 가능성이 있다고 의심되는 자기 자신을 호출하는 횟수를 집계하는 함수를 설정하면 됨   
// 그 횟수가 지정한 것보다 많으면 함수를 자동으로 종료시키도록 함   
- Therefore, it is important to design very carefully when creating a recursive function   
- You can set up a function that aggregates the number of calls to a self function suspected of being infinite recursive   
- Automatically shut down the function if the number of times is greater than specified   
   
<br />
### Another example of a factorial function   
// 계승 함수의 또다른 예시   
   
```javascript
function factorial(aNumber) {
    // If it is not an integer, discard the prime number
    aNumber = Math.floor(aNumber);
    // Rejects if it is less than 0
    if (aNumber < 0) {
        return "not a defined quantity";
    }
    // If it is 0 or 1, the factorial value is 1    
    if ((anumber == 0) || (anumber == 1)) {
        return 1;
    } else
    // Otherwise, it will be recursive until the end point is reached
        return (anumber * factorial(anumber - 1));
}
```
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
