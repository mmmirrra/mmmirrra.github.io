---
layout: post
title:  "JavaScript Html: javaScript Conditional Statement - Control Structure - for / for...in / for...of / forEach() / while / do...while"
date:   2023-12-13 09:00:00 +0900
categories: [JavaScript Html]
---

### for   
   
```html
<!DOCTYPE html>
<html>
    <head>
        <script>
            for (let i=0; i<10; i++) {
                console.log(i);
            };
        </script>
    </head>
    <body>
    </body>
</html>
```
   
<br />
### for...in   
It is a repetition that can be used for an object.   
It can also be used for arrays, but is not recommended for array iterations.   
   
```html
<!DOCTYPE html>
<html>
    <head>
        <script>
            const obj = {
                name: 'NAME',
                age: '20'
            }
            for (const key in obj) {
                console.log(key);                   // name // age
                console.log(obj.name, obj.age);     // NAME, 20
                console.log(`key: ${key}`);         // key: name // key: age
                console.log(`value: ${obj[key]}`);  // value: NAME // value: 20
            };
        </script>
    </head>
    <body>
    </body>
</html>
```
   
<br />
### for...of   
'for...of' is not supported by the Explorer.   
It can be used for repeatable objects (including array, map, set, string, typedArray, arguments, etc.).   
It is usually used for the array.   
   
```html
<!DOCTYPE html>
<html>
    <head>
        <script>
            const array = ['1', '2', '3'];
            for (const element of array) {
                console.log(element);           // array[first] value ~ array[last] value
                console.log(array);             // array full output
            };
        </script>
    </head>
    <body>
    </body>
</html>
```
   
<br />
### forEach()   
The Method used in the array.   
Use the callback function in the factor.   
   
```html
<!DOCTYPE html>
<html>
    <head>
        <script>
            const array = ['1', '2', '3'];
            array.forEach((element) => {
                console.log(element);           // array[first] value ~ array[last] value
            };
        </script>
    </head>
    <body>
    </body>
</html>
```
   
<br />
### while   
If while (condition) is false, it does not run once.   
   
```html
<!DOCTYPE html>
<html>
    <head>
        <script>
            const array = ['1', '2', '3'];
            while (array.length > 0) {               // condition
                array.forEach((element) => {
                    console.log(element);
                };
            }
        </script>
    </head>
    <body>
    </body>
</html>
```
   
<br />
### do...while   
do{} is executed at least once.   
After at least one execution, if the while condition is false, it is no longer executed.   
   
```html
<!DOCTYPE html>
<html>
    <head>
        <script>
            const array = ['1', '2', '3'];
            do{                                 // do{} is executed at least once.
                array.forEach((element) => {
                    console.log(element);
                };
            }
            while (array.length > 3)             // condition
        </script>
    </head>
    <body>
    </body>
</html>
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
