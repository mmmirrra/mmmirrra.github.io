---
layout: post
title:  "Git: Exclude - VSCode - Bash"
date:   2024-01-15 09:00:00 +0900
categories: [Git]
---

## To exclude a particular file name or directory from 'git'   
// 'git'에서 특정 파일명 또는 디렉토리를 제외하는 방법   
   
<br />
### Register file name or directory to be excluded through `vim.git/info/exlude`   
// 'vim .git/info/exclude' 으로 제외할 파일명 또는 디렉토리 등록   
   
<br />
#### 1. Type `vim.git/info/exlude` command and hit `Enter` to show 'git' list that allows you to list things to be excluded from 'git'   
// 'vim .git/info/exclude' 이 명령어 입력하고 'Enter'를 치면 'git'에서 제외할 목록 작성할 수 있는 'git' 화면 나옴   
   
```
vim .git/info/exclude
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/gitExclude1-1.png)
   
<br />
#### 2. Screen for creating a list to be excluded from 'git'   
// 'git'에서 제외할 목록을 작성하는 화면   
   
// 'a'를 누르면 입력할 수 있음   
Press `a` to enter   
   
// '# *~' 밑에 파일명 또는 디렉토리 입력. 입력한 다음에 'esc' 키 누르고 '- > :wq!' 입력한 다음에 'Enter' 치면 입력정보 저장되고 이 화면 종료됨   
Enter a file name or directory after `# *~`. Then press `esc` and type `->:wq!`, then hit `Enter` to save the input code and exit this screen   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/gitExclude1-2.png)
   
<br />
<br />
### You can exclude file names or directories one by one by entering commands into terminals (you must enter them one by one)   
// 터미널에서 명령어 입력하여 파일명 또는 디렉토리를 하나씩 제외할 수 있음 (하나씩 개별 입력해야 함)   
   
<br />
#### `git update-index –assume-unchanged` After this command, enter the file name or directory to exclude and press 'Enter'   
// 'git update-index --assume-unchanged' 이 명령어 뒤에 제외할 파일명 또는 디렉토리를 입력하고 'Enter' 치면 됨   
   
// 디렉토리 전체를 제외할 때는 디렉토리명 뒤에 '/'를 입력해야 함   
You must enter `/` after the directory name when excluding the entire directory   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/gitExclude2-1.png)
   
<br />
#### The entire directory is excluded by entering the directory   
// 디렉토리를 입력하여 디렉토리 전체가 제외된 경우임   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/gitExclude2-2.png)
   
<br />
#### The file name might not be recognized or the directory might not be found, leading to an error. In this case, you must register the file to be excluded from `vim.git/info/exlude`.   
// 파일명을 인식하지 못하거나 디렉토리를 찾지 못해서 오류날 수도 있음. 이런 경우에는 'vim .git/info/exclude' 에 제외할 파일 등록해야 함   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/gitExclude2-3.png)
