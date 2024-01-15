# Local Storage

> 영구 저장소 <br />
> 데이터를 브라우저에 저장하고, 브라우저를 종료해도 남아있다.

- key-value 형태로 데이터 저장
- 문자형 데이터 타입만 지원

# Session Storage

> 임시 저장소 <br />
> 데이터를 브라우저에 저장하고, 브라우저를 종료하면 삭제된다.

# Cookies

> 서버와 클라이언트가 지속적으로 데이터 교환을 하기 위해 만들어짐

- 서버가 사용자의 웹 브라우저에 전송하는 작은 데이터 조각
- 브라우저는 데이터 조각을 저장해 놓았다가 api 요청 시 자동으로 함께 전송함
- 동일한 서버에 재요청시 이 요청이 동일한 브라우저에서 들어왔는지 판단할 때 주로 사용된다.

## web storage (local storage, session storage)와 cookie의 차이점

<span style="color:#6BF2D9">Cookie</span>

- 쿠키를 설정하면 이후 모든 웹 요청은 쿠키를 포함해서 서버로 전송된다.

<span style="color:#F2996B">WebStorage</span>

- 데이터가 클라이언트(브라우저)에만 존재하고 서버로 전송되지 않는다.

<span style="color:#6BF2D9">Cookie</span>

- 용량이 제한된다.

<span style="color:#F2996B">WebStorage</span>

- 용량 제한이 없다.
