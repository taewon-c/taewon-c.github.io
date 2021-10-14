---
title: "[github] RSA방식의 deploy key 생성하기"
date: 2021-10-14T00:00:00+00:00
author: ttaka
layout: post
permalink: /generate-rsa-deploy-key/
categories: Genel
tags: [github, RSA]
---

`ssh-keygen -t rsa -b 4096 -m PEM`

**-m PEM** 의 옵션이 openssh 형식이 아닌 rsa 형식으로 Private Key 생성을 하게 해준다.