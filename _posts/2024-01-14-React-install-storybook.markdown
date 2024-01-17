---
layout: post
title:  "React: First installation - with Storybook"
date:   2024-01-14 09:00:00 +0900
categories: [React]
---

// 1. node.js 설치   
// 2. VScode 압축해제   
// 3. korean 언어패키지 설치 (옵션)   
// 4. 터미널창 오픈 - npx create-react-app "프로젝트명"   
// 5. 프로젝트 설치 완료 후 터미널창에서 'npm run build' 입력. 완료 후 'npm start' 입력   
// 6. 인터넷창에서 'localhost:3000' 으로 접속 시 화면이 동작하면 기본동작 완료   
   
1. Install node.js   
2. Unzip VScode   
3. Install Korean language package (optional)   
4. Terminal Window Open - npx create-react-app "Project Name"   
5. Enter `npm run build` in the terminal window after project installation is completed. Enter `npm start` after completion   
6. When accessing `localhost:3000` in the Internet window, when the screen is activated, complete   
   
<br />
#### Create `package.json` file   
// 'package.json' 파일 만들기   
   
```react
npm init -y
```
   
<br />
#### If yarn doesn't run, delete cache and try `yarn install` again   
// yarn 실행안되면 캐시 지우고 'yarn install' 다시 해보기   
   
```react
yarn cache clean --force
```
   
<br />
#### Upgrade the yarn version (-> This may clear the package settings)   
// yarn 버전 업그레이드 (-> 이거하면 패키지 설정 날아갈 수 있음)   
   
```react
yarn upgrade-interactive --latest
```
// 이거 입력한 뒤에 목록 나오면 선택   
Enter this and select when the list comes up   
// 'Ctrl + space' 누르면 전체 목록 선택됨   
Press `Ctrl + space` to select the full list   
// 'Shift + space' 누르면 개별 목록 선택됨   
Press `Shift + space` to select individual list   
   
<br />
#### Install Storybook (I erased the yarn cache)   
// Storybook 설치 (yarn 캐시 지우고 했음)   
   
```react
npx -p @storybook/cli sb init -f
```
   
<br />
#### When the Storybook does not run   
// Storybook 실행 안될 때   
   
```react
$env:NODE_OPTIONS = "--openssl-legacy-provider"
```
// 이거 입력한 뒤에 아래 명령어 실행   
Enter this and run the command below   
   
```react
yarn storybook
```
   
<br />
#### Upgrade the Storybook version (-> will delete the main.js setting)   
// Storybook 버전 업그레이드 (-> 이거하면 main.js 설정 날아감)   
   
```react
npx sb@next upgrade
```
