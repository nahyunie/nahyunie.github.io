---
title: 네트워크 통신 흐름 간단히 이해하기
date: "2024-07-14T00:00:00"
description: "브라우저에서 받은 데이터를 서버로 송출하기"
tags: ["Network"]
---

브라우저에서 서버로 데이터를 송출하는 과정을 그림으로 간단하게 표현하면 아래와 같다.


```scss
[네트워크 애플리케이션]
        |
    [소켓 API]
        |
   [네트워크 스택]
        |
   [LAN 드라이버]
        |
    [LAN 어댑터]
        |
[물리적 네트워크 매체]
```

#### 네트워크 애플리케이션
네트워크를 통해 다른 컴퓨터나 장치와 통신하거나 데이터를 주고받기위해 설계된 소프트웨어<br/>
**웹 브라우저**, **메일 서버**, **파일 전송 애플리케이션** 등이 있다.<br/>


#### 소켓 API
네트워크의 끝점(소켓)을 설정하고, 데이터 송수신을 관리한다. <br/>
소켓 API는 네트워크 애플리케이션에 포함된 한 기능이라고 볼 수 있다. <br/>

#### 네트워크 스택
운영체제에 내장된 네트워크 제어용 소프트웨어 <br/>

- **주요 프로토콜**
  - TCP: 데이터 송수신용 프로토콜. 일반적인 애플리케이션에서 사용.
  - UDP: 데이터 송수신용 프로토콜. DNS 서버 조회 등 짧은 제어용.
  - IP: 패킷 송수신용 프로토콜.
    - 패킷: 데이터를 작게 나눈 것

#### LAN 드라이버
LAN 드라이버는 하드웨어를 제어하고 통신한다.

#### LAN 어댑터
물리적 네트워크 매체(케이블, 무선 네트워크)에 대해 데이터를 송수신한다.


데이터가 네트워크로 전송되는 흐름을 간단하게 적어보았다. <br/>
더 상세한 내용은 추후에 다른 포스트로 다루어 보려고 한다. <br/>
