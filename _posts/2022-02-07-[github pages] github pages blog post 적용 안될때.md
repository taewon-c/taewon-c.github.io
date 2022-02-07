---
title: "[spring] @Autowired가 NullPointer Exception을 뱉는 경우"
date: 2022-02-03T22:00:00+00:00
author: ttaka
layout: post
permalink: /spring-di-autowired/
categories: Genel
tags: [spring]
---

아래 Stackoverflow의 설명을 간략히 요약함.

### 질문
- 컨트롤러에서 서비스를 호출하고 그 서비스 안에서는 다른 서비스를 @Autowired로 의존성 주입을 하고 있는데 NullPointerException이 떨어진다. 왜 그런가?

### 답변
- new 클래스명() 으로 컨트롤러에서 서비스를 생성하여 호출하고 있는데 그렇게 하면 Spring은 인지할 수 없다.
- IoC 컨테이너는 3가지 주요 로직을 가지고 있다.
  1. ApplicationContext에 등록된 components들에서
  2. context내의 bean들의 의존관계를 파악하고 
  3. dependency solver가 파악된 의존관계를 결정하고 초기화 하며 순서를 정한다.

- new 클래스()로 객체를 생성하면 JVM은 그 즉시 새로운 객체를 초기화하고 copy하며 위에서 말한 IoC 컨테이너가 그 의존관계를 파악할 수가 없다.

### 해결책
1. new 대신 @autowired를 통해 bean을 주입하시오
2. @Configurable로 new로 생성할 객체에 명시해라.



### 출처 
- https://stackoverflow.com/questions/19896870/why-is-my-spring-autowired-field-null







