---
layout: post
title:  "React: concept: tilde(~) and caret(^), the first letters of the react and node versions"
date:   2024-07-07 09:00:00 +0900
categories: [React]
---

// 리액트, 노드 버전앞에 붙는 tilde (~) 와 caret (^)   
tilde (~) and caret (^), the first characters of the react and node versions   
   
// 틸드 (~) : 지정한 버전의 마지막 자리 내 범위에서만 자동으로 업데이트 함.   
`tilde (~)` : Automatically updates only within the last digit range of the specified version.   
   
// 캐럿 (^) : 시맨틱 버전 설정 : MINOR나 PATCH버전은 하위호환성이 보장되어야 하므로 업데이트 함. Node.js나 npm의 모듈은 모두 시맨틱 버전을 따르고 있음.   
`caret (^)` : Semantic Versioning (== SemVer) : Update MINOR or PATCH versions as they must be backward compatible. Modules in Node.js or npm all follow SemVer.   
