# dynamic import

> import 구문을 사용하여 코드분할(Code Splitting)을 구현하는 방법

dynamic import는 React.lazy와 Suspense의 기능을 합친 것이다.

기본적으로 서버 컴포넌트는 자동으로 코드 분할되며, 스트리밍을 사용하여 서버에서 클라이언트로 UI 조각을 점진적으로 전송할 수 있다.

따라서 **지연 로딩은 클라이언트 컴포넌트에 적용**된다.

## 예시

```js
import dynamic from 'next/dynamic';

const DynamicComponent = dynamic(() => import('../components/DynamicComponent'));
```

위와 같이, next에서 제공하는 dynamic 함수를 사용해서 컴포넌트를 동적으로 로드할 수 있다.
