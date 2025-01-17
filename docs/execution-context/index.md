---
title: "실행 컨텍스트(Execution Context)"
description: ""
date: 2024-11-10 21:32:20
update: 2024-11-10 21:32:20
tags:
  - JavaScript/TypeScript
series: 
---

## 실행 컨텍스트, 왜 알아야 할까?

> 실행 컨텍스트는 마치 대상혁 같다. 자바스크립트의 모든 길은 실행 컨텍스트를 통한다.

실행 컨텍스트를 알아야 작성한 코드의 흐름을 이해, 제어 가능하다.
실행 컨텍스트를 이해하면 스코프 체인, 클로저, 호이스팅(Hoisting)을 자연스럽게 이해할 수 있다. 특히 비동기 코드의 흐름을 이해할 때 크게 도움 된다.

실행 컨텍스트를 이해하고 코드를 작성하면 엔진은 조금 더 적은 연산으로 코드를 실행한다. 이는 실행 컨텍스트를 알아야 하는 궁극적인 이유, 목적이다.

## 스코프 체인

> 거꾸로 강을 거슬러 오르는 저 힘찬 연어들처럼

스코프 체인이란 현재 실행 중인 실행 컨텍스트에서 변수를 조회할 수 없을 때, 이전 실행 컨텍스트로 이동하는 동작이다.
실행 컨텍스트는 체인처럼 서로 연결되어 있다.

## 마치며

깊게 알아볼 염두가 나지 않던 실행 컨텍스트에 한 발자국 다가갈 수 있는 시간을 보냈다. 가장 어려웠지만 아름답고 즐거운 시간을 보냈다. 자신감을 많이 얻었다.

실행 컨텍스트를 이해하면 다양한 부분을 제어할 수 있듯 배경지식을 꾸준히 쌓다 보면 다른 개념도 한 발자국 다가갈 수 있을 거라 믿어 의심치 않는다.

- [ ] 스코프 체인, 프로토타입 체인
- [ ] 스택, 링크드 리스트(스코프 체인)

- 대상혁, 모든 길은 실행 컨텍스트를 통합니다.
- 젠장 또 실행컨텍스트야

- 실행컨텍스트는 자바스크립트의 핵심, 전부다.
- 실행컨텍스트는 호이스팅, 클로저, 비동기 처리 방식등 다양한 개념을 접목시킬 수 있다.
- 실행 컨텍스트를 이해하기 위해서는 이전 과정이 탄탄해야 한다. 구멍이 뚫린 영역이 어디인지 명확하게 알 수 있다.
- 자료구조를 어느정도 알고 있어야 이해가 용이하다.
- 코어 자바스크립트를 함께 읽으면 이해가 조금 더 쉬울것 같다.
- 실행 컨텍스트를 기반으로 코드를 작성하면 엔진은 조금 더 적은 연산으로 코드를 실행한다. (알아야 하는 궁극적인 이유, 목적)

## 23.1 소스코드의 타입

- [ ] 소스코드 타입은 무엇을 의미하는가?
- [ ] 선언문으로 선언하는 방식은 무엇인가요? (변수 선언문, 함수 선언문)
- [ ] 스코프란 무엇인가요?

- 소스코드에 따라 다른 실행 컨텍스트를 생성한다.
- 모든 실행 컨텍스트는 평가와 실행 단계를 가진다.

## 23.2 소스코드의 평가와 실행

- (1) 자바스크립트는 소스를 평가한다. (2) 실행한다.

## 23.3 실행 컨텍스트의 역할

- 361 소스코드 평가 과정이 끝나면 비로소 **선언문**을 제외한 소스코드가 순차적으로 실행되기 시작한다. (변수 선언문, 함수 선언문)
- 363 스코프 체인
- 364 모든 코드는 실행 컨텍스트를 통해 실행되고 관리된다.
- 364 식별자와 스코프는 실행 컨텍스트의 렉시컬 환경으로 관리하고 코드 실행 순서는 실행 컨텍스트 스택으로 관리한다.

1. 식별자마다 스코프를 등록하여 관리한다.
2. 스코프 체인을 통해 함수를 실행하고 다른 스코프로 이동한다.

## 23.4 실행 컨텍스트 스택

- 365 실행 컨텍스트는 스택(stack) 자료구조로 관리된다. 이를 실행 컨텍스트 스택이라고 부른다.

## 23.5 렉시컬 환경

- 367 실행 컨텍스트는 Lexical Environment 컴포넌트와 Variable Environment 컴포넌트로 구성된다.
- 367 렉시컬 환경은 다음과 같이 두 개의 컴포넌트로 구성된다. Environment Record, Outer Lexical Environment Reference

1. Lexical Environment를 통해 스코프 체인을 구현한다?

렉시컬 환경이라는 용어가 익숙하지 않아서 직관적으로 이해되지 않는다.

## 23.6 실행 컨텍스트의 생성과 식별자 검색 과정

- [ ] 스코프 체인과 프로토타입 체인은 어떤 차이가 있을까?
- [ ] 호스트 객체란?
- [ ] 객체 환경 레코드와 선언적 환경 레코드
- [ ] 372 변수 호이스팅과 함수 호이스팅의 차이는 무엇인가요?
- [ ] TDZ(Temporal Dead Zone)란 무엇인가요? 선언은 했지만 참조할 수 없는 일시적인 상태.
- [ ] 예제 23-7를 설명하시오.


- 전역 코드가 평가되기 이전에 환경에 맞는 전역 객체가 생성된다. 예를들어 Window, Global
- 372 즉, 함수 선언문으로 정의한 함수는 함수 선언문 이전에 호출할 수 있다.
- 372 따라서 초기화 단계, 즉 런타임에 실행 흐름이 변수 선언문에 도달하기 전까지 일시적 사각지대(Temporal Dead Zone; TDZ)에 빠지게 된다.
