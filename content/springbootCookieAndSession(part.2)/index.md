---
emoji: 🪼
title: SpringBoot의 로그인 처리 쿠키와 세션(part.2 홈화면 개발)
date: '2023-12-06 20:12:00'
author: 아구
tags: SpringBoot login session cookie 쿠키와세션 로그인처리
categories: SpringBoot
imageUrl: 'springboot.png'
---

## 🎈 Start SpringBoot project 
- 이클립스(혹은 sts4)를 쓰고있다면 new project -> Spring Starter Project로 생성!

=====

## 🌵 회원 로그인 요구사항 정의
1. 홈화면 (로그인 전)
  * 회원 가입
  * 로그인
2. 홈화면 (로그인 이후)
  * 로그인 한 회원의 이름(oo님 환영합니다)이 보이기
  * 상품 관리 버튼
  * 로그아웃 버튼
3. 보안 요구사항 
  * 로그인 사용자만 상품에 접근하며, 아이템관리가 가능하다.
  * 만약 **로그인하지 않은 사용자가**접근시 로그인 화면으로 이동
4. 회원 가입, 상품 관리
`위와 같이 요구사항이 나왔다`
=====

## 🌚 화면 정의서
1. 홈화면 (로그인 전)
  ![before_login](before_login.png)

2. 홈화면 (로그인 후)
  ![after_login](after_login.png)

3. 회원가입
  ![singup_form](singup_form.png)

4. 로그인
  ![login_form](login_form.png)

5. 상품관리
  ![item_list](item_list.png)


## 🌂 패키지 구조
  * com.xxxxx.xxx
    * domain
      - item
      - member
      - login
    * web
      - item
      - member
      - login
  `도메인과 웹을 분리시키고, domain에서 web에 대한 의존성이 발생하면 안된다.`
  **도메인** : 화면,UI,기술 인프라 등등의 영역은 제외한 시스템이 구현해야 하는 핵심 비즈니스 업무 영역을 말함.
  이후 web을 다른 기술로 변경하더라도 도메인은 그대로 유지 할 수 있어야 함.
  이렇게 하려면 web은 domain을 알고 있지만, domain은 web을 모르도록 설계해야하는게 포인트다. 즉 의존성의 관계를 뜻한다.
  예를들어, 웹의 패키지를 모두 삭제해도 도메인에는 어떠한 영향도 있어선 안되게 설계하는것이 중요 하다.

- 이번편에서는 요구사항과 패키지 정리를 정해놓았고, 이후 요구사항과 패키지 정리에 맞추어 간단한 어플리케이션을 만들어 보도록 하겠다.

**to be continue...(홈화면 개발)**