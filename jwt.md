# JWT

> Json Web Token , 인터넷 표준 인증 방식

Json 객체에 인증에 필요한 정보들을 담은 후 비밀키로 서명한 토큰

## JWT의 구조

- Header, Payload, Signature
  - Header : alg(Signature에서 사용하는 알고리즘)/typ(토큰 타입)
  - Payload : 클레임(claim) 정보들 <br />
    <span style="color:#E6574C">\*claim? payload에 담는 정보의 한 조각을 클레임이라고 한다. (name-value)</span>
  - Signature : 헤더와 페이로드의 문자열을 합친 후 주어진 비밀키로 해쉬한 값
