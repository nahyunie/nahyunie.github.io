---
title: URL과 URL 구조
date: "2024-07-07T01:00:00"
description: "사용자는 브라우저 주소창에 URL을 입력한다."
tags: ["Network"]
---

사용자가 브라우저 주소창에 URL을 입력하면 어떤 일이 일어날까?<br/>
그 전에 **URL**과 **URL 구조**에 대해 알아보자.

### URL
URL은 간단하게 말해 리소스가 저장되어 있는 위치를 지정하는 주소를 말한다.<br/>
주로 `http:`와 `https:`를 많이 보게 되지만 그 외에도 `ftp:`, `file:`, `mailto:` 등 다양하다.<br/>
이것의 이름을 **URL 스킴(URL Scheme)** 이라고 하는데 리소스에 접근하는 방식을 정의한 것이다. <br/>

- 웹이라면 `http:` 
- FTP 서버라면 `ftp:` 
- 파일 시스템이라면 `file:`
- 이메일이라면 `mailto:`
<br/>
URL을 작성하는 방법은 URL 스킴에 따라 다르다.<br/>
도메인 명/파일 경로/메일 주소 등이 들어갈 수도 있고, 때에 따라 사용자명, 비밀번호, 포트번호 등도 사용한다.<br/>
eg) `https://www.example.com:8080/path/to/resource`, <br/> `ftp://username:password@ftp.example.com/public/file.txt`

<br/>그 다음 **브라우저**는 입력된 URL을 **해독**한다.

해독하는 과정의 첫번째는 바로 URL 파싱이다.<br/>
URL은 다음과 같은 요소로 분해된다.<br/>



➀ **URL 스킴**: `http:`<br/>
➁ **호스트명**: `www.example.com`<br/>
➂ **포트번호**: `8080` (지정된 경우만)<br/>
➃ **경로**: `/dir/index.html`<br/>
➄ **쿼리문자열**: `tab=repositories` (선택 사항)<br/>

`http://www.example.com/dir/index.html` 의 경우는 dir 디렉터리에 있는 index.html을 엑세스한다는 의미이다.<br/>
하지만, 모든 URL 구조가 정확한 파일 경로를 가지고 있는 건 아니다.<br/><br/>
아래 다섯가지 예시를 보자.

##### ➀ www.example.com/dir/index.html
- **www.example.com** 서버에 있는 **/dir** 디렉터리 내 **index.html** 파일을 요청<br/>

##### ➁ www.example.com/dir/
- **www.example.com** 서버에 있는 **/dir** 디렉터리를 요청
- 디렉터리 내 기본 파일 (서버에서 설정한 파일, 보통 index.html)을 반환
- 기본 파일이 없는 경우 디렉터리 목록을 반환<br/>

##### ➂ www.example.com/
- **www.example.com** 서버에 있는 루트 디렉터리를 요청
- 루트 디렉터리 내 기본 파일 (index.html, index.php 등)
##### ➃ www.example.com
- ➂과 같이 루트 디렉터리 요청
- '/'(슬래시)가 생략되었지만 브라우저와 서버에서 보완함
##### ➄ www.example.com/whatisthis
- **www.example.com** 서버에 있는 whatisthis라는 리소스 요청
- 파일일수도 디렉터리일수도 있음
- whatisthis라는 파일이 존재 시 파일 반환, 디렉터리가 있으면 디렉터리 반환(둘 다 존재할 수는 없다.)
- 둘 다 존재하지 않는다면 404 반환

URL을 해독한 후 브라우저는 HTTP를 사용하여 웹 서버에 엑세스 한다.