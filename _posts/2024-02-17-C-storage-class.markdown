---
layout: post
title:  "C: Storage Class"
date:   2024-02-17 09:00:00 +0900
categories: [C]
---

storage class : How to assign a variable to a specific area of storage space   
   
#### Depending on where the variable is used   
 - local variable   
 - global variable   
   
#### Depending on the initialization, duration and range of validity of the variable   
 : Example of use : storageClass datatype variable;   
   
|type|Example of use|Description|
|:---|:---|:---|
|`auto`<br />// 자동변수|auto int a;|Created at the execution of the function, and removed storage space at the end of the execution.<br />You can skip "auto".<br />It's a local variable.<br />Initialization required.|
|`static`<br />// 정적변수|static int a;|Storage space is maintained until the end of the program.<br />It's a global variable.<br />The value of the variable continues during program execution.<br />Initialized to 0 if no initialization|
|`extern`<br />// 외부변수|extern int a;|Declared outside of the function.<br />It's a global variable.<br />Values of variables declared as external variables can be referenced in other files.<br />Initialized to 0 if no initialization.|
|`register`<br />// 레지스터변수|register int a;|Used to store data in registers within the CPU.<br />Property is the same as the auto variable.<br />Used to increase the execution speed of a program.<br />Mainly used as counter variable in Loop statement.|
