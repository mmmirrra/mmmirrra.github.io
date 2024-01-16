---
layout: post
title:  "Git: Error - Eclipse"
date:   2024-01-16 09:00:00 +0900
categories: [Git]
---

## How to fix an error when running 'git > pull'   
// 'git > pull' 실행 시 발생한 오류 해결하는 방법   
   
<br />
### How to ignore my local file and overwrite it with 'git' file   
// 내 로컬 파일은 무시하고 'git' 파일로 덮어쓰는 방법   
   
// 터미널에서 실행할 파일이 있는 디렉토리까지 진입하여 'checkout' 실행해보기   
`git checkout directory` : Enter the directory with files to run through the terminal and try 'checkout'   
   
<br />
#### Example   
Run 'git checkout filename' from 'mobile-be-api' folder on drive d:   
'git checkout' is a feature that ignores my local file and overwrites it with the file 'git'   
// d 드라이브의 'mobile-be-api' 폴더에서 'git checkout 파일명' 실행함: 'git checkout'은 내 로컬 파일은 무시하고 'git'의 파일로 덮어쓰는 기능임   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/gitError1-1.png)
   
<br /><br />
### How to fix errors that occur during build after 'git > pull'   
// 'git > pull' 이후 빌드 시 오류 발생하는 경우 해결 방법   
   
<br />
#### 1. Project > Clean   
   
// 'git' 파일은 모두 일치시켰는데 오류가 있으면 프로젝트를 클린하고 빌드를 다시 해볼 수 있음. 빌드는 보통 자동으로 실행되지만 가끔 안되는 경우가 있으므로 강제로 해봄.   
If you have matched all 'git' files and there is an error, you can try to clean and rebuild the project.   
Builds usually run automatically, but are forced to do so if sometimes it can't.   
   
// 'git' 외에도 빌드 시 오류 발생하는 경우 이 방법으로 해결해 볼 수 있음   
In addition to 'git', this can be resolved if an error occurs during the build   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/gitError2-1.png)
   
<br />
#### 2. Maven > Update Project   
   
// 프로젝트명 위에서 마우스 오른쪽 버튼 클릭 > 메뉴 목록에서 'Maven' > 'Update Project...' 선택 : 정보 업데이트 되어 빌드 됨   
Right-click on the project name > Select 'Maven' > 'Update Project...' from the menu list : Updated information and built   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/gitError2-2.png)
