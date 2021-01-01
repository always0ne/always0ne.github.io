---
title: [스프링부트로 Rest API 만들어보기] 스프링? 스프링부트? 뭐가 다르죠?
excerpt: about springboot
toc: true
toc_sticky: true
categories:
    - server
    - springboot
tags:
    - server
    - springboot
last_modified_at: 2021-01-01T23:17:00-09:00
---
## Spring
우리가 흔히 스프링이라고 알고 있는것은 spring framework 이다.  
Spring framework 은 초기 J2EE 사양의 복잡성을 대응하기 위해 2003년에 시작된 오픈소스 프로젝트이다.
[(프로젝트 명인 Spring은 J2EE의 겨울 이후 새로운 시작을 의미한다고 한다.)](https://spring.io/blog/2006/11/09/spring-framework-the-origins-of-a-project-and-a-name)
인프라적인 부분을 스프링이 처리해주어 POJO(Plain Old Java Object)기반으로 개발자가 개발에만 집중할 수 있도록 하는것이 목적이다.
spring framework 외에도 spring boot, spring security, spring data, spring cloud, spring batch 등 여러 프로젝트가 있다.
주요 웹 프레임워크로는 Spring MVC(동기), Spring Flux(비동기)가 있다.

### 주요 개념
스프링을 사용하면서 알아야 할 주요 개념들이다. 우선은 간단하게 설명 한 후 자세한 내용은 이후의 포스팅에서 서술하겠다.
#### 의존성 주입(DI) 및 제어반전(IOC)
기존에는 객체간 의존성은 개발자가 객체를 생성하면서 제어를 했지만 스프링 프레임워크에서는 컨테이너가 이런 객체들의 생명주기를 제어를 한다. 
이 현상을 제어의 반전이라고 하고, 객체를 사용하고 싶을 땐 해당클래스에 의존성 주입을 해서 사용한다. 의존성 주입은 여러가지가 있지만 생성자를 이용한 의존성 주입이 가장 권장된다.
#### POJO
POJO 는 Plain Old Java Object 의 약자이다. 특별한 제한에 종속되지 않는 일반적인 Java 객체를 의미한다. 쉽게말하면 프레임워크에 종속된 무거운 객체를 만들지 말자는 것이다.  
자바의 객체지향적인 특징을 살려 비즈니스 로직에 충실한 개발이 가능하도록 하는것에 가치를 둔다.
#### AOP
Abstract Oriented Programming 의 약자로 관점 지향 프로그램이라고 한다. 업무로직을 포함하는 핵심기능 외에 로깅, 보안을 담당하는 부가기능들을 분리해서 모듈화 하는것이다.
객체지향에서 이 부분을 구현하기 어렵기 때문에 이러한 부가기능들을 Aspect 라는 모듈형태로 만들어서 설계하고 개발을 진행한다. Spring AOP는 프록시 기반 AOP를 제공한다.
정해진 타겟의 호출을 가로챈 다음 로직을 수행한 후, 핵심기능인 로직을 호출하는 방식이다. 
#### MVC
MVC(Model-View-Controller) 패턴은 소프트웨어 아키텍처중 한 패턴이다.화면, 제어, 데이터의 역할을 서로 독립시켜준다.
처리순서는 아래와 같다.
```
1. Controller가 사용자의 요청을 받는다
2. 비즈니스 로직을 처리한 후 Model을 조작한다.
3. Model의 데이터를 기반으로 View를 제어하여 사용자에게 반환한다.
```
#### DTO
Data Transfer Object 의 약자이다. 단순히 데이터 교환을 위한 논리가 없는 순수한 객체이다. getter 나 setter, 생성자만 있는 객체이다.
#### DAO
Data Access Object 의 약자이다. DB를 사용해 데이터를 조회하거나 조작하는 기능을 전담하는 객체이다. 

## Spring Boot
앞에서 스프링이 개발자가 개발에만 집중할 수 있도록 하는것이 목적이라고 했다. 분명 이전보다는 훨씬 편해진것은 맞으나 이마저도 기능이 많아 환경설정이 복잡하다는 문제가 있었다.
그 부분을 해소하기 위하여 이런 설정의 많은 부분을 자동화 하여 더욱 편하고, 빠른시간에 제품을 만들 수 있도록 하는것을 목표로 진행되는 프로젝트이다.
간단한 spring-boot-stater-로 시작하는 의존성만 추가해주면 내장된 톰켓, 기본설정들로 빠르게 시작할 수 있다.

## 마무리
지금까지 Spring Framework에 대하여 간략하게 알아보았다. 매우 잘 설계된 Framework이라는 생각이 든다.  
이 시리즈는 스프링을 처음 사용하는 사람들을 위해 작성되고 있기 때문에 이후에서는 Spring Boot로 설명을 진행하겠다.