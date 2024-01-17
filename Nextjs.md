# Nextjs

> React 기반의 프레임워크

<span style="color:#E6574C"></span>

페이지 기반의 라우팅 및 서버 사이드 렌더링(SSR), 정적 사이트 생성(SSG) 등을 지원하여 개발자들이 빠르고 효율적으로 웹 애플리케이션을 구축할 수 있도록 도와준다.
([\*SSR&SSG](SSR&SSG.md))

## Next.js version 13

Next.js가 버전 13으로 업데이트되면서 기존의 pages 디렉터리 구조에서 app directory 구조로 변경됐다.

### <span style="color:#F266AA">🌟 pages -> app directory (App Router)</span>

#### <span style="color:#7066F2">page 라우터</span>

```
/page/post.tsx 👉 http://localhost:3000/post
```

기존에는 page 폴더에서 웹사이트의 페이지 컴포넌트를 처리했다.

#### <span style="color:#7066F2">App 라우터</span>

```
/app/post/page.tsx 👉 http://localhost:3000/post
```

App라우터는 폴더 내에 page 컴포넌트를 작성하면 해당 폴더명으로 라우팅이 이뤄진다.

또한, 같은 폴더 내에 layout 파일을 정의하여 여러 페이지 간에 UI를 공유할 수 있다. <br />

☀️ app directory내부에서는 모든 컴포넌트가 기본적으로 서버컴포넌트로 동작한다 ☀️
<br />
(app directory 내부에서 클라이언트 컴포넌트를 사용하고 싶으면 최상단에 'use client'를 명시해줘야한다.)

<span style="color:#00F5B9">**RSC (React Server Component) & RCC (React ClientComponent)**</span>

둘의 차이는 이름에서도 나타나듯이 컴포넌트가 렌더링되는 곳이 서버냐 클라이언트냐의 차이다.

따라서, 컴포넌트의 역할이 어떤지에 따라 알맞은 방법으로 컴포넌트를 정의하면 된다.

역할에 따른 구분

- 데이터를 가져온다 👉 <span style="color:#F4394D">RSC</span>
- 백엔드 리소스에 접근 👉 <span style="color:#F4394D">RSC</span>
- 민감한 정보를 서버에 보관 (ex. Access Token, API KEY 등..) 👉 <span style="color:#F4394D">RSC</span>
- 서버에 대해 큰 종속성 유지 👉 <span style="color:#F4394D">RSC</span>
- 상호작용 및 이벤트 리스너(ex. onChange, onClick..) 추가 👉 <span style="color:#38C2F5">RCC</span>
- 브라우저 전용 API 사용 👉 <span style="color:#38C2F5">RCC</span>
- 상태 관리 메서드, 라이프 사이클 메서드, custom Hook 사용 (ex. useState, useEffect...) 👉 <span style="color:#38C2F5">RCC</span>

### <span style="color:#F266AA">getServerSideProps 👉 getStaticProps(App Directory)</span>

**기존에는 (Next13 이전)**

data fetch 등을 수행할 때 반드시 getServerSideProps(또는 getStaticProps) 함수를 page 최상단에서 수행하고, 이를 page에 prop으로 넘겨서 사용했어야 했다.

**Next 13에서는**

기본적으로 서버 컴포넌트(RSC)로 동작하기 때문에 컴포넌트 자체가 서버에서 렌더링되기 때문에 컴포넌트 내부에서 fetch를 실행하면 된다.

### <span style="color:#F266AA">그 외 변화들</span>

#### <span style="color:#7066F2">Image</span>

Nextjs 12 버전에서 임시적으로 `next/future/image`를 통해 개선된 이미지 컴포넌트를 사용할 수 있었다.
클라이언트 측 javascript 코드 양을 줄이고, 더 쉽게 이미지를 확장하고 스타일링하며, 더 나은 접근성과 native browser lazyloading을 제공해주었다.

13버전부터는 이러한 기능들이 `next/image` 에서도 기본적으로 적용된다.

#### <span style="color:#7066F2">Link</span>

Link 컴포넌트를 사용할 때 더이상 a 태그를 child 노드로 넣어줄 필요 없다. <br />
version 12에서 실험적인 옵션으로 추가되었었는데 13버전부터 디폴트 기능이 되었다.

#### <span style="color:#7066F2">Font Optimization</span>

이전에는 font를 최적화하기 위해 인라인 css 속성을 주었었다.
버전 13부터는 `next/font` 모듈이 추가되어서 이를 사용해서 폰트를 최적화하고 커스터마이징 할 수 있다.

## 참고

- [Next) 서버 컴포넌트(React Server Component)에 대한 고찰](https://velog.io/@2ast/React-%EC%84%9C%EB%B2%84-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8React-Server-Component%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B3%A0%EC%B0%B0#next13%EA%B3%BC-server-component)
