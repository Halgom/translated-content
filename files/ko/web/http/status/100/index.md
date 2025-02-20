---
title: 100 Continue
slug: Web/HTTP/Status/100
tags:
  - HTTP
  - Informational
  - Status code
translation_of: Web/HTTP/Status/100
---
{{HTTPSidebar}}

HTTP **`100 Continue`** 정보 상태 응답 코드는 클라이언트가 서버로 보낸 요청에 문제가 없으니 다음 요청을 이어서 보내도 된다는 것을 의미합니다. 만약 클라이언트의 작업이 완료되었다면 이 응답은 무시해도 됩니다.

클라이언트가 서버로 하여금 이를 검토하게 하려면 첫 번째 요청에서 {{HTTPHeader("Expect")}}`: 100-continue`를 헤더로 보내야 합니다. 이후, 클라이언트는 본문을 보내기 전에 서버가 `100 Continue` 상태 코드로 응답하길 기다려야 합니다.

## 상태

```
100 Continue
```

## 명세

{{Specifications}}

## 브라우저 호환성

{{Compat("http.status.100")}}

## 같이 보기

- {{HTTPHeader("Expect")}}
- {{HTTPStatus(417)}}
