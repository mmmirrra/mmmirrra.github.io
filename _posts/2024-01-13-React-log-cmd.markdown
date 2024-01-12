---
layout: post
title:  "React: How to check logs in cmd
cmd log prompt"
date:   2024-01-12 09:00:00 +0900
categories: [React]
---

### At the command prompt, enter the directory where the file you want to run and try running it   
// 명령 프롬프트에서 실행할 파일이 있는 디렉토리까지 진입하여 실행해보기   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/reactLogsCmd.png)
   
<br>
#### Description of 1 // 1에 대한 설명   
   
// d 드라이브의 `SPC9_20230406 > ssr-recipe` 폴더에서 `node scripts/build.server.js` 명령어 실행함   
Executed command 'node scripts/build.server.js' in folder 'SPC9_20230406> ssr-recipe' on drive d   
   
#### Description of 2 // 2에 대한 설명   
   
// 'ValicationError' 발생한 예시: ‘option’은 알 수 없는 값이라고 함. 가능한 값 중에 ‘options’가 있음. `scripts/build.server.js` 파일에서 ‘option’을 ‘options’로 수정해서 재실행하니 오류없이 실행됨   
Example of 'ValidationError': 'option' is an unknown value. Among the possible values, there is 'options'. In the file 'scripts/build.server.js', 'option' was modified to 'options' and re-executed. Runs without errors.   
