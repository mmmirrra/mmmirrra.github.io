---
layout: post
title:  "PuTTY: How to connect PuTTY"
date:   2024-01-15 09:00:00 +0900
categories: [PuTTY]
---

### You can access it by entering 'Host Name(or IP address)', 'Port' and selecting the 'Open' button. Select the remaining options based on the project situation.   
// 'Host Name(or IP address)', 'Port' 입력 후 'Open' 버튼 선택하면 접속할 수 있음. 나머지 옵션은 프로젝트 상황에 따라 선택   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/puttyConnect.png)
   
<br>
#### How to view real-time logs   
   
// 방법 1. 로그인 한 뒤 './로그파일명logs.sh'를 입력하고 'Enter' 치면 실행됨   
// 방법 2. 'tail -f /디렉토리/로그파일명.log'를 입력하고 'Enter' 치면 실행됨   
// 방법 3. '/디렉토리/로그파일명logs.sh'를 입력하고 'Enter' 치면 실행됨   
   
1. After logging in, type './log filename logs.sh' and type 'Enter' to execute   
2. Run by typing 'tail -f / directory/log filename.log' and 'Enter'   
3. Run by typing '/directory/log filename logs.sh' and 'Enter'   
   
<br>
#### Log file location : The location of the 'logfile name.log' file varies depending on the project   
// 로그 파일 위치 : 프로젝트에 따라 '로그파일명.log' 파일의 위치가 다름   
