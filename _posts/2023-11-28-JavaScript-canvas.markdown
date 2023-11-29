---
layout: post
title:  "JavaScript: canvas"
date:   2023-11-28 09:00:00 +0900
categories: [JavaScript]
---

### example   
`
<script>
    function callCanvas() {
        let canvas = document.getElementById('myCanvas');
        let ctx = canvas.getContext('2d');
        ctx.font = "20px 굴림체";
        ctx.fillStyle = "red";
        ctx.fillText("캔버스 맛보기", canvas.width/2-70, canvas.height/2-5);
        ctx.strokeStyle = "blue";
        ctx.strokeRect(70, 40, 200, 100);
    };
</script>
<body onload="callCanvas();">
    <canvas id="myCanvas" width="350px" height="200px" style="border: 1px solid red; background-color: lightgreen">
        이 브라우저는 HTML5의 canvas 요소를 지원하지 않습니다.
    </canvas>
</body>
`
   
{% highlight html %}
<!DOCTYPE html>
<html>
    <head>
        <script>
            function callCanvas() {
                let canvas = document.getElementById('myCanvas');
                let ctx = canvas.getContext('2d');
                ctx.font = "20px 굴림체";
                ctx.fillStyle = "red";
                ctx.fillText("캔버스 맛보기", canvas.width/2-70, canvas.height/2-5);
                ctx.strokeStyle = "blue";
                ctx.strokeRect(70, 40, 200, 100);
            };
        </script>
    </head>
    <body onload="callCanvas();">
        <canvas id="myCanvas" width="350px" height="200px" style="border: 1px solid red; background-color: lightgreen">
            이 브라우저는 HTML5의 canvas 요소를 지원하지 않습니다.
        </canvas>
    </body>
</html>
{% endhighlight %}
