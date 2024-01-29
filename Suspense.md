# Suspense

> Suspense를 사용하면 컴포넌트가 렌더링되기 전에 다른 작업이 먼저 이뤄지도록 대기한다.

리액트 컴포넌트 내부에서 비동기적으로 다른 요소를 불러올 때 해당 요소가 불러와질 때까지 컴포넌트의 렌더링을 잠시 멈추는 용도로 사용할 수 있는 컴포넌트

## 비동기 데이터 관리 라이브러리

suspense를 지원하는 라이브러리들이 있다.

- Relay
- SWR
- React-Query
- Recoil

Suspense와 비동기 데이터를 이용해 로딩 로직을 짤 수 있는 이유는
Suspense가 Promise를 catch하는데
위와 같은 라이브러리에서 Promise 상태를 throw 하는 기능을 제공하기 때문이다.

따라서 Promise가 resolve되기 전까지 Suspense가 fallback UI를 보여줄 수 있게된다.

## 참고

[Suspense을 사용해 선언적으로 로딩 화면 구현하기](https://lasbe.tistory.com/160)
