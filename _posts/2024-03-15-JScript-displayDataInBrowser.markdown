---
layout: post
title:  "JScript: How to display Data in Internet Explorer Browser"
date:   2024-03-15 09:00:00 +0900
categories: [JScript]
---

// JScript에는 브라우저에 데이터를 직접 표시하는 방법이 두 가지 있음   
// 사용자는 document 개체의 write()와 writeIn() 메서드를 사용할 수 있음   
// 또한 형식을 갖춘 정보를 브라우저 안의 폼에 표시할 수 있을 뿐만 아니라 경고, 프론프트, 확인 메시지 상자에도 표시할 수 있음   
- JScript has two ways to display data directly in your browser   
- Users can use the write() and writeIn() methods of document objects   
- In addition, formatting information can be displayed in a form within a browser, as well as in a warning, forward, or confirmation message box   
   
<br />
### Using document.write() and document.writeIn()   
// document.write()와 document.writeIn() 사용   
   
// 정보를 표시하는 데 가장 많이 사용하는 방법은 document 개체의 write() 메서드를 사용하는 것임   
// 여기에는 브라우저에 표시할 인수 한 개, 즉 문자열 한 개가 필요함   
// 이 문자열은 일반 텍스트이거나 HTML임   
- The most common way to display information is to use the write() method of the document object   
- This requires one argument (i.e. one string) to be displayed in the browser   
- This string is plain text or HTML   
   
// 문자열은 작은따옴표나 큰따옴표로 묶을 수 있음   
// 이렇게 하면 따옴표나 아포스트로피를 포함하는 내용을 인용할 수 있음   
- String can be enclosed in single quotation marks or double quotation marks   
- This way, you can quote the content that includes quotes or apostrophes   
   
```javascript
document.write("PI value is approximately " + Math.PI);
document.write();
```
   
// 아래 나오는 간단한 함수는 브라우저 창에 표시할 내용이 있을 때마다 `document.write`를 입력해야 하는 방법을 보여줌   
// 이 함수는 사용자가 쓰려는 것이 정의되지 않았는지 여부를 알려주지는 않지만 `w();` 명령을 수행할 수는 있음   
// `w();` 명령은 빈 줄을 표시함   
- The simple function below shows how to enter `document.write` whenever there is something to display in the browser window   
- This function does not confirm whether what the user is trying to write is defined, but it can execute the command `w();`   
- Command `w();` shows empty lines   
   
```javascript
function w(m)
{
    // m 변수가 문자열임을 확인
    // - Verify that m variable is a string
    m = "" + m + "";
    // 빈 내용이나 정의되지 않은 항목을 테스트
    // - Test for blanks or undefined items
    if("undefined" != m)
    {
        document.write("<br>");
    }

    w('<IMG SRC="horse.gif">');
    w();
    w("This is a carving of words");
    w();
}
```
   
// writeIn() 메서드는 write() 메서드와 거의 동일하지만 모든 문자열에 줄바꿈 문자를 추가한다는 점이 write() 메서드와 다름   
// HTML에서 일반적으로 항목 뒤에 공백이 생길 뿐이지만 `<PRE>` 태그와 `<XMP>` 태그를 사용하는 경우에는 줄바꿈 문자를 그대로 해석하여 브라우저에 표시함   
- The writeIn() method is almost identical to the write() method, but differs from the write() method in that it adds a new line character to all strings   
- In HTML, there is only a space after an item, but if you use the `<PRE>` and `<XMP>` tags, interpret the new line characters as they are and display them in your browser   
   
// write() 메서드를 호출할 경우 문서가 열려서 구문 분석되고 있지 않으면 write() 메서드는 문서를 열고 내용을 지우기 때문에 위험함   
// 아래 예시는 1분마다 시간을 표시하려고 만들었지만 처리 도중에 지워져 처음에만 실행되는 스크립트임   
- If you call the write() method, the write() method is dangerous because it opens the document and clears the contents if the document is not parsed   
- The example below is a script that is created to display time every minute, but is erased during processing and runs only for the first time   
   
```html
<HTML>
    <HEAD>
        <SCRIPT LANGUAGE = "JScript">
            function singOut()
            {
                var theMoment = new Date();
                var theHour = theMoment.getHours();
                var theMinute = theMoment.getMinutes();
                var theDisplacement = (theMoment.getTimezoneOffset() / 60);
                theHour -= theDisplacement;

                if(theHour > 23)
                {
                    theHour -= 24;
                }
                document.write(theHour + " hours, " + theMinute + " minutes, Coordinated Universal Time");
                window.setTimeout("singOut();", 60000);
            }
        </SCRIPT>
    </HEAD>
    <BODY>
        <SCRIPT>
            singOut();
        </SCRIPT>
    </BODY>
</HTML>
```
   
// document.write() 대신 창 개체의 alert() 메서드를 사용할 경우 이 스크립트는 정상적으로 사용됨   
- If you use the alert() method of a window object instead of document.write(), this script is used normally   
   
```javascript
window.alert(theHour + " hours, " + theMinute + " minutes, Coordinated Universal Time");
window.setTimeout("signOut();", 60000);
```
   
<br />
### Clear current document   
// 현재 문서 지우기   
   
// document 개체의 clear() 메서드는 현재 문서를 지움   
// 이 메서드는 문서의 나머지 부분과 함께 스크립트도 지우기 때문에 주의를 기울여 사용해야 함   
- Clear() method of document object cleared current document   
- This method should be used with caution because it also clears the script along with the rest of the document   
   
```javascript
document.clear();
```
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
