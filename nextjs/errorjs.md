# error.js

error.js 파일을 사용하면 라우트 세그먼트에 대한 에러 UI를 정의할 수 있다.

이 파일을 정의하면 서버나 클라이언트 컴포넌트에서 발생하는 예기치 못한 오류를 잡아내고 fallback UI를 보여줄 수 있어서 유용하다.

## Props

`error`

error.js 클라이언트 컴포넌트로 전달된 Error 객체의 인스턴스

`reset`

해당 함수를 실행하면 Error boundary의 컨텐츠를 리렌더링합니다. 렌더링 성공 시, 결과가 보여집니다.

## global-error

최상단(root)에서 error를 처리하고 싶다면, app directory의 global-error.js 파일을 정의하면 된다.

## not-found.js

not-found.js 파일은 라우트 세그먼트 내에서 notFound() 함수가 throw될 때 UI를 렌더링하는 데 사용된다.

## 참고

[공식문서](https://nextjs.org/docs/app/api-reference/file-conventions/error#global-errorjs)
