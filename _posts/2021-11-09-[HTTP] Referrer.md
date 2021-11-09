---
title: "[HTTP] Referrer"
date: 2021-11-09T20:35:00+00:00
author: ttaka
layout: post
permalink: /http-referrer/
categories: Genel
tags: [http]
---

HTTP 헤더에 있는 Referer는 이전 방문 페이지를 나타낸다.
이는 어디서 유입되었는지를 나타내기도 하고 비정상적인 루트로 들어오는 Request를 체크하기도 한다.

html페이지에서 다른곳으로 request를 날릴때 설정할 수 있다.
아래의 content에 어떤 값을 설정하느냐에 따라 옵션이 변경된다.

```html
<meta name="referrer" content="xxx">
```










