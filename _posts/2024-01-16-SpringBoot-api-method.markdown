---
layout: post
title:  "Spring Boot: Method type to map REST API to controller"
date:   2024-01-16 09:00:00 +0900
categories: [SpringBoot]
---

#### 1. POST   
C : CREATE, INSERT   
   
#### 2. GET / POST   
R : SELECT   
   
// ※ 목록과 상세가 있는 경우 'GET'을 써서 파라미터를 보내주면 백 버튼 기능을 구현하기 편함   
※ If there is a list and details, it is easy to implement the back button function by sending parameters using `GET`   
   
#### 3. PUT / POST   
U : UPDATE   
   
#### 4. DELETE   
D : DELETE   
   
<br />
### API Sample   
   
```java
package com.study;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.ResponseBody;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

@Controller
public class RestApiTestController {

    @GetMapping("/members")
    @ResponseBody           // public @ResponseBody List<Map<String, Object>> findAllMember()와 같이 리턴 타입 앞에도 선언 가능
    public List<Map<String, Object>> findAllMember() {

        List<Map<String, Object>> members = new ArrayList<>();

        for (int i = 1; i <= 20; i++) {
            Map<String, Object> member = new HashMap<>();
            member.put("id", i);
            member.put("name", i + "번 개발자");
            member.put("age", 10 + i);
            members.add(member);
        }

        return members;
    }

}
```
