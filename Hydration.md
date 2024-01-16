# Hydration

SSR이나 SSG를 통해 pre-rendering 된 HTML을 클라이언트 측에서 interactive하게 만드는 과정

([\*SSR&SSG](SSR&SSG.md))

## React.hydrate()

React는 DOM에 리액트 컴포넌트를 렌더링해주는 render 함수를 제공한다.

```
ReactDOM.render(element,container[,callback])
```

- 특정 컴포넌트를 두 번째 파라미터인 지정된 DOM 요소에 하위로 주입하여 렌더링을 처리해준다.
- 렌더링이 완료되면 특정 이벤트를 처리할 콜백 함수를 세 번째 파라미터로 넣어줄 수 있다.

## React.hydrate()

```
ReactDOM.hydrate(element,container[,callback])
```

- `hydrate()`는 `render()`와 동일하지만 ReactDOMServer에서 HTML 컨텐츠를 렌더링 한 container를 hydrate하는데 사용된다.

- 렌더링을 통해 새로운 웹 페이지를 구성할 DOM을 생성하는 것이 아니라, 기존 DOM Tree에서 해당되는 DOM 요소를 찾아 정해진 자바스크립트 속성(이벤트 리스너 등)들을 추가하기 위해 사용된다.

즉, 서버사이드렌더링을 통해 이미 마크업이 채워져있는 경우 다시 render할 필요가 없기 때문에 hydrate를 사용해서 "이벤트 핸들러 함수들"을 정적인 DOM 노드에 붙여서 동적으로 상호작용이 가능하도록 해주는 것이다.

\*\* React18 부터는 hydrate 가 hydrateRoot로 대체되었다. (👉[공식문서](https://react.dev/reference/react-dom/hydrate))

## 선택적인 hydration

react18에서 업데이트된 내용 <br />
hydration의 우선순위가 클릭 대상 컴포넌트로 설정됨으로써 time to interactive 문제 개선

## 참고

- [hydration이란?](https://velog.io/@chltjdrhd777/React-hydration%EC%9D%B4%EB%9E%80-root%EB%9E%80)
- [ReactDOM.hydrate()](https://velog.io/@xortm854/ReactDOM.hydrate)

- [Hydrate(Next,React18)](https://velog.io/@leehyunho2001/Hydrate)
