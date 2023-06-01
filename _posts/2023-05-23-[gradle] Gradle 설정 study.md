---
title: "[gradle] Gradle 설정 study"
date: 2023-05-23T15:00:00+00:00
author: ttaka
layout: post
permalink: /gradle-study/
categories: Genel
tags: [gradle]
---


# Gradle Multi Project
## root settings.gradle
```kt
rootProject.name = '프로젝트 이름' //프로젝트 이름 지정

include(":multi-module-name") //하위 프로젝트 include
```

## build.gradle

- `allprojects` 
  - 현재 프로젝트와 모든 서브 프로젝트에 적용시킬것들.

- `subprojects`
  - 서브 프로젝트들만 접근함 

## 빌드 의존성
- 루트 프로젝트에서 빌드를 실행하면 알파벳 순서로 subprojects를 실행