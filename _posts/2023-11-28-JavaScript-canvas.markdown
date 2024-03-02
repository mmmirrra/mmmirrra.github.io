---
layout: post
title:  "JavaScript: canvas"
date:   2023-11-28 09:00:00 +0900
categories: [JavaScript Html]
---

### example   
`
<script>
    function callCanvas() {
        let canvas = document.getElementById('myCanvas');
        let ctx = canvas.getContext('2d');
        ctx.font = "20px Arial";
        ctx.fillStyle = "red";
        ctx.fillText("Example of making a canvas", canvas.width/2-70, canvas.height/2-5);
        ctx.strokeStyle = "blue";
        ctx.strokeRect(70, 40, 200, 100);
    };
</script>
<body onload="callCanvas();">
    <canvas id="myCanvas" width="350px" height="200px" style="border: 1px solid red; background-color: lightgreen">
        <!-- 이 브라우저는 HTML5의 canvas 요소를 지원하지 않습니다. -->
        This browser does not support the canvas element in HTML5.   
    </canvas>
</body>
`
   
```html
<!DOCTYPE html>
<html>
    <head>
        <script>
            function callCanvas() {
                let canvas = document.getElementById('myCanvas');
                let ctx = canvas.getContext('2d');
                ctx.font = "20px Arial";
                ctx.fillStyle = "red";
                ctx.fillText("Example of making a canvas", canvas.width/2-70, canvas.height/2-5);
                ctx.strokeStyle = "blue";
                ctx.strokeRect(70, 40, 200, 100);
            };
        </script>
    </head>
    <body onload="callCanvas();">
        <canvas id="myCanvas" width="350px" height="200px" style="border: 1px solid red; background-color: lightgreen">
            <!-- 이 브라우저는 HTML5의 canvas 요소를 지원하지 않습니다. -->
            This browser does not support the canvas element in HTML5.   
        </canvas>
    </body>
</html>
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
