# React Query -> TanStack Query (v5)

> v5 부터 React18과 Typescript 4.7이상의 버전에서만 사용 가능

## v5 변화

### suspense를 지원하는 hooks

- useSuspenseQuery
- useSuspenseInfiniteQuery
- useSuspenseQueries

🌟 useQuery에서 사용하던 `suspense:boolean` 옵션은 제거되고 해당 훅을 사용한다.<br />
🌟 로딩과 에러 상태를 Suspense와 ErrorBoundary가 처리하기 때문에 status가 언제나 success인 data를 반환한다.

## 참고

[TanStack Query v5 정식 버전 살펴보기](<https://www.moonkorea.dev/React-TanStack-Query-v5-%EC%82%B4%ED%8E%B4%EB%B3%B4%EA%B8%B0-(%EB%A6%AC%EC%95%A1%ED%8A%B8%EC%BF%BC%EB%A6%AC)#usemutationstate%EB%A1%9C-mutation-%EC%83%81%ED%83%9C-%EA%B3%B5%EC%9C%A0>)
