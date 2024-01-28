# react-query

> 앱의 서버 상태를 쉽게 관리(캐싱, 동기화 및 업데이트)할 수 있게 해주는 라이브러리

## SSR

React Query는 서버에서 데이터를 미리 가져와서 해당 데이터를 queryClient로 전달하는 두 가지 방법을 지원한다.

- 데이터를 직접 미리 가져와서 `initialData`로 전달
- 서버에서 쿼리를 미리 가져와서 캐시를 dehydrate하고 클라이언트에서 rehydrate

## Using Nextjs

이러한 메커니즘의 정확한 구현은 플랫폼에 따라 다를 수 있지만, react-query에서는 2가지 형태(SSG, SSR)의 사전 렌더링을 지원하는 Next.js로 시작하는 것을 권장한다.

## 참고

[Next.js 13에서 React Query SSR 적용하는 방법](https://velog.io/@ckstn0777/Next.js-13%EC%97%90%EC%84%9C-React-Query-SSR-%EC%A0%81%EC%9A%A9%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)
