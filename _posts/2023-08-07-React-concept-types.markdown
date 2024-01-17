---
layout: post
title:  "React: concept: @types How to use it"
date:   2023-08-07 09:00:00 +0900
categories: [React]
---

// 타입스크립트에서 써드 파티 라이브러리를 사용하려면 각 기능에 대한 타입이 정의되어 있어야 함.   
TypeScript requires a type defined for each function to use a third-party library.   
   
// 써드 파티 라이브러리 사용이 안되는 이유 : 타입스크립트에 제이쿼리 라이브러리의 내부 코드에 대한 타입이 정의되어 있지 않아서 제이쿼리 라이브러리를 들고 와서 사용할 때 타입을 추론할 수 없음. 이런 경우 'react-router-dom' 대신 '@types/react-router-dom' 를 설치해야 함.   
Why third-party libraries are unavailable : TypeScript does not define a type for the internal code of the JQuery Library, so it cannot infer the type when importing and using the JQuery Library. In this case, `@types/react-router-dom` must be installed instead of `react-router-dom`.   
