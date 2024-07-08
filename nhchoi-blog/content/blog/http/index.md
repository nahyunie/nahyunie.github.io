---
title: HTTP 요청과 응답
date: "2024-07-07T02:00:00"
description: "브라우저는 HTTP를 사용하여 웹 서버에 엑세스한다."
tags: ["Network"]
---

브라우저는 입력받은 URL을 해독한 후 HTTP를 사용하여 웹 서버에 엑세스 한다.<br/>
그런데, **HTTP**가 뭐지?

### HTTP
클라이언트(웹 브라우저)와 서버(웹 서버) 간의 데이터를 주고받기 위한 프로토콜.<br/>
인터넷 상에서 웹 페이지를 전달하는 가장 기본적인 통신규약

**클라이언트는 HTTP 요청을 보내고 서버는 HTTP 응답을 반환한다.**

#### HTTP 요청(HTTP Request)
- 요청 줄(Request Line): **메서드**, URL, HTTP 버전 포함
- 헤더(Header)
- 바디(Body): 선택 사항

##### 주요 메서드
1. GET
2. POST
3. PUT
4. DELETE

#### HTTP 응답(HTTP Response)
- 상태 줄(Status Line): HTTP 버전, **상태 코드(Status Code)**, 상태 메세지
- 헤더(Header)
- 바디(Body)

##### 주요 상태 코드
1. 200 OK: 요청이 성공적으로 처리되었음
2. 400 Bad Request: 잘못된 요청임
3. 401 Unauthorized: 인증이 필요함
4. 404 Not Found: 요청한 리소스를 찾을 수 없음
5. 500 Internal Server Error: 서버 오류가 발생했음


#### 주요 헤더 필드
##### 제너럴 헤더
- Date: 작성된 날짜
- Connection: 연결 방식
##### 리퀘스트 헤더
- Accept: 클라이언트가 수신할 수 있는 콘텐츠 타입
- User-Agent: 요청을 보내는 클라이언트(브라우저)의 정보
- Host: 요청하는 서버의 호스트 이름
##### 응답 헤더
- Server: 서버의 소프트웨어와 버전 정보를 포함
##### 엔티티 헤더
- Content-Type: 응답 본문의 데이터 타입
- Content-Length: 응답 본문의 길이를 바이트 단위로 나타냄
- Expires: 캐시된 응답의 만료 날짜와 시간을 나타냄
<br/>

>  **Content-Type: text/html** 일 때
>
>  HTML 문서 안에 포함된 이미지나 영상 등의 리소스들은 필요에 따라 추가적인 HTTP 요청을 통해 받아오게 된다.<br/>
> 이미지나 다른 리소스가 별도의 URL로 제공되고 있을 경우, 클라이언트는 해당 리소스에 대해 별도의 HTTP 요청을 보낸다.<br/>
> 예를 들어, `<img src="image.jpg">`와 같은 경우 이미지 파일 'image.jpg'를 따로 요청하여 받아옴.<br/>
> 만약, 문서 안에 세 개의 리소스가 포함되어 있다면 HTTP 요청을 총 4번 보내게 되는 것이다.