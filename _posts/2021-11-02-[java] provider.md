---
title: "[java] Provider"
date: 2021-11-02T21:00:00+00:00
author: ttaka
layout: post
permalink: /java-provider/
categories: Genel
tags: [java]
---

기본적으로 스프링에서 빈을 등록하면 싱글톤으로 만들어진다.

```java
@Autowired
private TestClass bean1;
@Autowired
private TestClass bean2;

public void singletonTest(){
    /* 결과 값이 같음 */
    System.out.println(bean1.hashCode());
    System.out.println(bean2.hashCode());
}
```

하지만 bean을 호출할때마다 새로운 인스턴스를 얻고 싶으면 Bean의 scope을 prototype으로 설정한다.

```java
@Service
@Scope("prototype")
public class TestClass{

}

//-------------------------------------------//

@Autowired
private TestClass bean1;
@Autowired
private TestClass bean2;

public void protoTypeTest(){
    /* 결과 값이 다름 */
    System.out.println(bean1.hashCode());
    System.out.println(bean2.hashCode());
}
```

위와 같은 prototype scope bean을 받는 방법에는 여러가지가 있지만
그 중에서 <em>javax.inject.Provider</em>로 받는 방법을 적는다.

Provider는 get() 메소드로 prototype bean을 호출한다.

```java
@Service
@Scope("prototype")
public class TestClass{

}

//-------------------------------------------//

@Inject
private Provider<TestClass> bean;

public void ProviderTest(){
    /* 결과 값이 다름 */
    System.out.println(bean.get());
    System.out.println(bean.get());
}
```

