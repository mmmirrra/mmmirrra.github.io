---
layout: post
title:  "JScript: Message Box"
date:   2024-03-15 09:00:00 +0900
categories: [JScript]
---

### Use alert, prompt, and confirmation message boxes   
// 경고, 프롬프트 및 확인 메시지 상자 사용   
   
// 사용자가 입력한 값을 받아들이기 위하여 경고, 확인 및 프롬프트 메시지 상자를 사용함   
// 이 상자들은 인터페이스 window 개체의 메서드들임   
// window 개체는 개체 계층 구조의 맨 위에 있으므로 실제로 `window.alert()`처럼 이 메시지 상자들의 전체 이름을 사용할 필요는 없음   
// 그러나 메시지 상자가 어느 개체에 속하는지를 기억하는데 도움이 되므로 전체 이름을 사용하는 것이 좋음   
- To accept the value entered by the user, use the Alert, Confirm, and Prompt message boxes   
- These boxes are methods for the interface window object   
- The window object is at the top of the object hierarchy, so you don't actually need to use the full name of these message boxes like `window.alert()`   
- However, it is recommended to use a full name because it helps you remember which object the message box belongs to   
   
### Warning Message Box   
// 경고 메시지 상자   
   
// 경고 메서드는 한 개의 인수를 가짐   
// 이 인수는 사용자에게 보여주려는 텍스트 문자열이며, HTML이 아님   
// 경고 메시지 상자에는 확인 단추가 있어 사용자가 메시지 상자를 닫을 수 있음   
// 그리고 이 상자는 모달이므로 작업을 계속하려면 메시지 상자를 닫아야 함   
- Warning method has one argument   
- This argument is a text string that you want to show the user. This is not HTML   
- A warning message box has a confirmation button that allows users to close the message box   
- And this box is modal, so you need to close the message box to continue working   
   
```javascript
window.alert("Welcome! Press OK to continue");
```
   
### Confirmation Message Box   
// 확인 메시지 상자   
   
// 확인 메시지 상자는 사용자가 "예 또는 아니오"로 대답할 수 있도록 질문하고 사용자는 확인 단추 또는 취소 단추를 누르면 됨   
// confirm 메서드는 true 또는 false 중 하나를 반환함   
// 이 메시지 상자 역시 모달임   
// 사용자는 반드시 메시지 상자에 응답해야하며(어느 단추든 눌러야 함), 상자를 닫은 후에야 작업을 계속할 수 있음   
- The confirmation message box asks the user to answer yes or no, and the user presses the confirmation button or the cancel button   
- The confirm method returns either true or false   
- This message box is also modal   
- Users must respond to the message box (press any button) and can only continue working after closing the box   
   
```javascript
var truthBeTold = window.confirm("Press OK to continue and Cancel to stop");
if(truthBeTold)
{
    window.alert("Welcome to our web page!");
}
else window.alert("Goodbye!");
```
   
### Prompt Message Box   
// 프롬프트 메시지 상자   
   
// 프롬프트 메시지 상자는 프롬프트에 대한 답변을 입력할 수 있는 텍스트 필드를 제공함   
// 이 메시지 상자에는 확인 단추와 취소 단추가 있음   
// 사용자가 두번째 문자열 인수를 입력하면 프롬프트 메시지 상자는 텍스트 필드에 두번째 문자열을 기본 응답으로 표시함   
// 그렇지 않으면 기본 텍스트는 "<undefined>"임   
- The prompt message box provides a text field for users to enter answers to prompts   
- This message box has a confirmation button and a cancel button   
- When a user enters a second string argument, the prompt message box displays the second string as the default response in the text field   
- Otherwise, the default text is "<undefined>"   
   
// alert() 메서드 및 confirm() 메서드와 같이 prompt 메서드는 모달이므로, 작업을 계속하려면 프롬프트 메시지 상자를 닫아야 함   
- As with the alert() method and confirm() method, the prompt message box must be closed to continue the operation because the prompt method is a modal   
   
```javascript
var theResponse = window.prompt("Welcome!", "Please enter your name here");
```
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
