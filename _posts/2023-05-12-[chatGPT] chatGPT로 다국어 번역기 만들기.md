---
title: "[kotlin] 코틀린 입문(코드제어)"
date: 2023-05-11T15:00:00+00:00
author: ttaka
layout: post
permalink: /kotlin-2/
categories: Genel
tags: [kotlin]
---

_(본 내용은 해당 강의를 보고 공부를 위해 요약한 자료입니다. 출처 : https://www.inflearn.com/course/java-to-kotlin/dashboard)_

# 코틀린에서의 코드제어
## 코틀린에서 변수를 다루는 방법
### 변수 선언 키워드 - var / val
- var : 수정가능
- val : 수정 불가능
- 타입을 명시적으로 작성해 줄 수 있다.
- 초기화
  - 초기값을 정해주지 않는 경우는 타입을 명시해줘야하고 변수를 사용하려면 값을 초기화 해줘야 한다.
    ```kt
    var number: Int
    pringtln(number) // Variable 'number' must be initialize
    ```
- 코드를 클린하게 가꾸기 위한 Tip
  - 모든 변수는 우선 val로 만든고 꼭 필요한 경우 var로 변경

### Kotlin에서의 Primitive Type 
- 코틀린이 알아서 컴파일할때 알아서 변형해준다.
- 즉, 프로그래머가 boxint / unboxing을 고려하지 않아도 되도록 Kotlin이 알아서 처리 해준다.

### Kotlin에서의 nullable 변수
- 기본적으로 모든 변수를 null이 들어갈 수 없게 설계해놨다.
```kt
var number = null // error!
var number: Long?
```

### Kotlin에서의 객체 인스턴스화
- kotlin에서 객체 인스턴스화를 할 때에는 new를 붙이지 않아야 한다.
```kt
val person = Person("xxx")

```






