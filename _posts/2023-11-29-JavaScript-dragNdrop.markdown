---
layout: post
title:  "JavaScript: drag & drop"
date:   2023-11-29 09:00:00 +0900
categories: [JavaScript]
---

### example   
`
<script>
    function dragstart(event) {
        event.dataTransfer.setData("text", event.target.id);
        event.dataTransfer.effectAllowed = "move";
        let img = new Image();
        img.src = "drag.jpg";
        event.dataTransfer.setDragImage(img, 20, 20);
    };
    function dragover(event) {
        event.preventDefault();
    };
    function drop(event) {
        event.preventDefault();
        let data = event.dataTransfer.getData("text");
        event.target.appendChild(document.getElementById(data));
        event.dataTransfer.dropEffect = "move";
    };
</script>
<style>
    #div1, #div2 { width: 100px; height: 100px; border: 1px solid; padding: 10px; margin: 5px; }
    #div1 { background-color: lightyellow; }
    #div2 { background-color: lightgreen; }
</style>
<body>
    <div id="div1" ondrop="drop(event)" ondragover="dragover(event)">
        <img id="image" src="flower.jpg" width="100px" height="100px" draggable="true" ondragstart="dragstart(event)" alt="">
    </div>
    <div id="div2" ondrop="drop(event)" ondragover="dragover(event)"></div>
</body>
`
   
```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            #div1, #div2 { width: 100px; height: 100px; border: 1px solid; padding: 10px; margin: 5px; }
            #div1 { background-color: lightyellow; }
            #div2 { background-color: lightgreen; }
        </style>
        <script>
            function dragstart(event) {
                event.dataTransfer.setData("text", event.target.id);
                event.dataTransfer.effectAllowed = "move";
                let img = new Image();
                img.src = "drag.jpg";
                event.dataTransfer.setDragImage(img, 20, 20);
            };
            function dragover(event) {
                event.preventDefault();
            };
            function drop(event) {
                event.preventDefault();
                let data = event.dataTransfer.getData("text");
                event.target.appendChild(document.getElementById(data));
                event.dataTransfer.dropEffect = "move";
            };
        </script>
    </head>
    <body>
        <div id="div1" ondrop="drop(event)" ondragover="dragover(event)">
            <img id="image" src="flower.jpg" width="100px" height="100px" draggable="true" ondragstart="dragstart(event)" alt="">
        </div>
        <div id="div2" ondrop="drop(event)" ondragover="dragover(event)"></div>
    </body>
</html>
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
