---
layout: post
title:  "Spring Boot: What is JWT?"
date:   2024-01-16 09:00:00 +0900
categories: [SpringBoot]
---

#### jwt is json form : divided into three parts   
// jwt는 json 형태임 : 세가지 형태로 나뉘어짐   
   
// 1. '헤더 Header'에는 토큰 타입과 서명 알고리즘 저장   
// 2. '페이로드 Payload'에는 '클라임 Claim'이라는 사용자 또는 토큰 property를 key-value 형태로 저장   
// 3. '시그니처 Signature'에는 jwt 정보 저장   
   
1. `Header` stores token types and signature algorithms   
2. `Payload` stores a user named `Claim` or token property in key-value format   
3. Save jwt information in `Signature`   
   
<br />
#### Three-letter abbreviation used as the name of the key according to the standard specification: Choose according to the situation and use it   
// 표준 스펙상 key의 이름으로 사용하는 3글자 약어 : 상황에 따라 골라서 사용   
   
<br />
// 'sub' : 인증 주체 : 토큰 제목 : 토큰에서 사용자에 대한 식별 값이 됨   
`sub` : subject : Token title: Identification value for user in token   
// 'iss' : 토큰 발급처   
`iss` : issuer   
// 'typ' : 토큰의 유형   
`typ` : type   
// 'alg' : 서명 알고리즘   
`alg` : algorithm   
// 'iat' : 토큰 발급 시각   
`iat` : issued at   
// 'exp' : 토큰 만료 시작   
`exp` : expiration time   
// 'aud' : 클라이언트 : 토큰 대상자   
`aud` : audience : Token Targets   
// 'nbf' : 토큰 활성 날짜   
`nbf` : not before   
// 'jti' : JWT 토큰 식별자 : Issuer가 여러 명 일 때 구분하기 위한 값   
`jti` : JWT ID : Values to differentiate when there are multiple Issuers   
   
```json
Header
{
    “typ”: “JWT”,
    “alg”: “HS512”
}

Payload
{
    “sub”: “1”,
    “iss”: “ori”,
    “exp”: 163698718,
    “iat”: 163698718,
}

// Payload를 커스텀하여 커스텀한 Claim을 만드는 경우
Create a custom Claim by customizing Payload
{
    “token_type”: “access token”
}

Signature
{
    HMACSHA512(
        base64UrlEncode(header) + “.” +
        base64UrlEncode(payload),
        your-256-bit-secret
    ) secret base64 encoded
}
```
