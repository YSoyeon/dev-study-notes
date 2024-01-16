# Nextjs

Nextjs는 브라우저 렌더링 시 기본적으로 pre-rendering을 해준다. <br />
<span style="color:#E6574C">\*pre-rendering(사전 렌더링)?</span>
<span style="color:#6E55EA">\*서버</span>에서 이미 build된 HTML 문서를 렌더링하는 것

<br />

<span style="color:#918DEB">\*<span style="color:#6E55EA">**서버** </span>: Nextjs가 자체적으로 가지고 있는 웹 서버</span>

pre-rendering을 하는 방법은 SSG와 SSR로 나뉜다.
둘의 차이는 HTML을 생성하는 시기에 있다.

# SSR

> Server-Side-Rendering

유저가 페이지를 <span style="color:#E6574C">**요청할 때마다**</span> HTML문서가 생성된다. <br />
SSR을 사용하기 위해서는 매 요청마다 서버에 의해호출되는 `getServerSideProps` 함수를 사용하는 것이 필요하다.

SSR은 항상 최신 상태를 유지해야하는 웹페이지나 분석차트 등 사용자의 요청마다 동적으로 페이지를 생성해서 다른 내용을 보여줘야 하는 경우 사용될 수 있다.

### CSR과의 차이

기존 React에서는 CSR 방식으로 데이터를 가져올 때 useEffect를 사용했다면, Nextjs에서는 `getServerSideProps`, `getStaticProps`, `getStaticPaths`등을 활용해서 데이터를 불러온다.

- `getServerSideProps`
  : Nextjs가 pre-rendering을 할 때, 이 함수를 발견하면 컴포넌트 함수 호출 전에 이 함수를 먼저 호출한다.<br />
  api통신을 통해 데이터를 받아온 후 컴포넌트에 props로 데이터를 전달한다.
  <br />
  매 요청마다 호출되며 서버에서 실행된다.

# SSG

<span style="color:#E6574C">**빌드 시 HTML이 생성**</span>되고 매 요청마다 <span style="color:#E6574C">**HTML을 재사용**</span>한다.
(CDN으로 캐시)

SSG는 마케팅 페이지나 블로그 게시물과 같이 정적으로 생성된 정보를 요청마다 동일한 정보로 반환하는 경우 사용된다.

- `getStaticProps`
  : Nextjs에서 SSG를 사용해서 데이터를 받아오려면 이 함수를 사용하면 된다.<br /> 서버 측에서만 실행되는 함수여서 클라이언트에서는 실행되지 않는다.<br />
  이 함수는 api와 같은 외부 데이터를 받아서 정적생성하기 위한 용도이며 빌드 시 <span style="color:#E6574C">**딱 한 번만 호출**</span>되어 static file로 빌드된다.
- `getStaticPaths`
  : `/posts/[id].js` 와 같이 동적 라우터를 사용해서 id에 따라 다른 페이지를 보여주고 싶을 경우 사용할 수 있다. (즉, path가 외부 데이터에 의존하는 경우)<br />
  이 함수를 사용해서 pre-rendering되기 원하는 path들을 명시해줄 수 있다.

## 상황에 따라 다른 렌더링 방식을 적용한다.

- Pre-rendering이 필요없다면 👉 `CSR`
- 정적 문서(ex.소개 페이지)로 충분하다면 👉 `SSG`
- 컨텐츠가 동적이지만 자주 변경되지 않는 경우(ex.블로그) 👉 `ISR`
- 매 요청마다 화면이 달라지며 pre-rendering이 필요하다면 👉 `SSR`

## 참고

- [Next.js의 렌더링 방식 이해하기 - SSR, SSG, ISR](https://enjoydev.life/blog/nextjs/1-ssr-ssg-isr)
