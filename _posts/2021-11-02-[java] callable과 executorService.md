---
title: "[java] callable과 executorService"
date: 2021-11-02T22:00:00+00:00
author: ttaka
layout: post
permalink: /java-callable-executorService/
categories: Genel
tags: [java]
---

Callable을 설명하기 위해 Runnable과 비교해본다.

#### 공통점
둘다 스레드에 의해 실행되어지도록 설계되었다는 공통점이 있다.

#### 차이점 
- Runnable : 어떤 객체도 리턴하지 않는다. Exception을 발생시키지 않는다.
- Callable : 특정타입의 객체를 리턴한다. Exception을 발생시킬 수 있다.

#### Runnable 사용예제
```java
public class RunnableTest {
    static class RunnableClass implements Runnable {
        @Override
        public void run(){
            System.out.println("test");
        }
    }

    public static void main(String[] args){
        RunnableClass rc = new RunnableClass();
        Thread thread = new Thread(rc);
        thread.start();
    }
}
```

Callable은 ExecutorService로 실행시킬 수 있고 결과를 리턴받을 수 있다.

ExecutorService는 쓰래드풀을 생성하여 병렬처리를 수행할 수 있다.

#### Callable ExecutorService 사용예제
```java
public class CallableTest {
    static class CallableClass implements Callable<String> {
        @Override
        public String call() throws Exception{
            return "test";
        }
    }

    public static void main(String[] args) throws Exception{
        CallableClass callable = new CallableClass();
        ExecutorService executor = Executors.newSingleThreadExecutor();
        Future<String> future = executor.submit(callable);

        System.out.println(future.get());
    }
}
```

ExecutorService는 아래를 참고하면 이해가 쉽다.
[ExecutorService 설명](https://codechacha.com/ko/java-executors/)



