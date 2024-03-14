---
layout: post
title:  "JScript: Data Copy, Forward, Compare"
date:   2024-03-14 09:00:00 +0900
categories: [JScript]
---

### Transmission by value and transmission by reference   
// 값에 의한 전달과 참조에 의한 전달   
   
// 숫자와 부울값(true와 false)는 값에 의한 전달로 복사, 전달, 비교됨   
- Numbers and Boolean values (true and false) are copied, transmitted, or compared as transfer by value   
   
// 값에 의한 전달로 복사 또는 전달하면 컴퓨터 메모리에 공간을 지정한 후 원래 값을 그 공간 안에 넣음   
// 그리고나서 원본을 변경하더라도 두 항목은 별개의 것이기 때문에 복사본은 영향을 받지 않음   
// 반대의 경우도 마찬가지임   
- Copying or forwarding by value specifies a space in computer memory and places the original value in that space   
- Then even if you change the original, the copy is not affected because the two items are separate   
- It's the same effect in the opposite case   
   
// 대부분의 경우 개체, 배열 및 함수는 참조에 의한 전달로 복사, 전달, 비교됨   
// 참조에 의한 전달로 복사 또는 전달하면 원래 항목에 대한 포인터를 만들어 그 포인터를 복사본처럼 사용함   
// 그리고나서 원본을 변경하면 원본과 복사본이 모두 바뀜   
// 반대의 경우도 마찬가지임   
// 실제로 항목은 하나만 존재함   
// 즉, "복사본"은 실제로 복사본이 아니라 항목에 대한 또다른 참조일 뿐임   
- In most cases, objects, arrangements, and functions are copied, transferred, and compared by transfer by reference   
- Copying or passing by reference creates a pointer to the original item and uses that pointer as a copy   
- Then changing the original changes both the original and the copy   
- It's the same effect in the opposite case   
- Only one item actually exists   
- In other words, "copy" is actually just another reference to an item, not a copy   
   
// assign() 메서드를 사용하면 개체와 배열의 이런 동작을 변경할 수 있음   
- The assign() method allows you to change this behavior of objects and arrays   
   
// 문자열을 복사, 전달할 때는 참조에 의한 전달만 사용하지만 비교할 때는 값에 의한 전달을 사용함   
- Use only forwarding by reference when copying and forwarding a string, but forwarding by value when comparing   
   
// ASCII와 ANSI 문자 집합의 구성 방식 때문에 대문자는 시퀀스 순서에서 소문자보다 앞에 옴   
// 예를 들어, "Zoo"는 "aardvark"보다 앞에 옴   
- Capital letters precede lowercase letters in sequence order because of how ASCII and ANSI character sets are constructed   
- For example, "Zoo" precedes "aardvark"   
   
### Delivering parameters to a function   
// 함수로 매개변수 전달   
   
// 값에 의한 전달로 함수에 매개변수를 전달하면 함수 안에서만 존재하는 별도의 매개 변수 복사본을 만들게 됨   
// 이와는 달리 참조에 의한 전달로 함수에 매개변수를 전달한 후 함수에서 해당 매개변수의 값을 변경하면 스크립트 내의 모든 부분에서 해당 매개변수의 값이 변경됨   
- Delivering parameters to a function by value results in the creation of separate copies of parameters that exist only within the function   
- Alternatively, if you pass a parameter to a function by 'transfer by reference' and then change the value of that parameter in the function, the value of that parameter changes in all parts of the script   
   
### Data Test   
// 데이터 테스트   
   
// 값에 의한 전달로 테스트를 수행할 때는 별개의 두 항목을 비교하여 서로 같은지 봄   
// 보통, 이 비교는 바이트를 단위로 하여 이루어짐   
// 참조에 의한 전달로 비교할 때에는 두 항목이 한 원본 항목에 대한 포인터인지 봄   
// 두 항목이 한 원본 항목에 대한 포인터인 경우에는 두 항목이 같은 것으로 보고, 그렇지 않은 경우에는 비록 두 값이 바이트 단위로 비교하여 완전히 일치한다고 해도 서로 다른 것으로 봄   
- When performing a test by value, compare two separate items to see if they are the same   
- Usually, this comparison is done in bytes   
- See if two items are pointers to one source item when compared to forwarding by reference   
- If two items are pointers to one source item, they are considered to be the same. Otherwise, even if the two values are completely identical in comparison in bytes, they are considered different   
   
// 문자열을 참조에 의한 전달로 복사, 전달하면 메모리를 절약할 수 있음   
// 그러나 일단 만든 문자열을 변경할 수 없기 때문에 값에 의한 전달로 문자열을 비교할 수 있음   
// 이렇게 하면 서로 완전히 독립적으로 생성된 두 문자열의 내용이 일치하는지 테스트할 수 있음   
- Copying and transferring strings to forwarding by reference saves memory   
- However, once the string you created cannot be changed, you can compare the strings by transfer by value   
- This allows you to test whether the contents of two strings generated completely independently of each other match   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
