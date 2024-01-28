# 서버 상태 관리

서버로 부터 받아온 데이터를 관리하는 것을 말한다. 대표적인 상태 관리 라이브러리로 `react-query`와 `swr`이 있다.

서버에서 데이터를 가져오고 (data fetching), 데이터 캐싱, 동기화, 업데이트 등을 지원한다.

## `swr` vs `react-query`

#### 🌹 `SWR`

1. 캐시에서 데이터를 반환한 다음
2. 서버에 데이터를 가져오는 요청을 보내고
3. 최신 데이터를 가져온다.

위와 같은 전략을 가진다.

👉 즉, 빠르게 캐시 데이터로 렌더링하고(우선순위👆), 최신의 데이터를 가져온다.

#### ☀️ `react-query`

react 앱에서 서버 상태를 가져오고 캐싱하고 동기화하고 업데이트하는 것을 쉽게 해준다.

👉 즉, API 호출로 받아온 데이터를 쉽게 관리할 수 있도록 지원해주는 라이브러리다.

### 예제

#### 🌹 `SWR`

```typescript
const fetcher = (url) => axios.get(url).then((res) => res.data);
const TodoList = () => {
	const { data, error, isValidating } = useSWR("http://localhost:3000/todo-list", fetcher);

	if (error) return <div>failed to load</div>;
	if (!data) return <div>loading...</div>;

	return <List data={data} />;
};
```

- 두 번째 인자로 fetcher를 받는다. 이때, fetcher의 인자로 swr의 첫번째 인자를 넘겨받는다.
- `isValidating`을 통해 상태를 표현할 수 있다.

#### ☀️ `react-query`

```ts
import { QueryClient, QueryClientProvider, useQuery } from "react-query";

const App = () => {
	const queryClient = new QueryClient();

	<div>
		<QueryClientProvider client={queryClient}>
			<TodoList />
		</QueryClientProvider>
	</div>;
};
```

- react-query를 사용할 때는 꼭 최상단 컴포넌트에서 `QueryClientProvider`를 정의해줘야한다.

```ts
const fetchTodos = () => {
	return axios.get("http://localhost:3000/todo-list");
};
const TodoList = () => {
	const { isLoading, error, data, isFetching } = useQuery("todos", fetchTodos);

	if (error) return <div>failed to load</div>;
	if (isLoading) return <div>loading...</div>;

	return <List data={data} />;
};
```

- fetcher에 url을 직접 넘겨줘야한다.
- `isLoading` , `isFetching`을 통해 데이터의 상태를 보여준다. <br />
  (`ìsFetching`은 첫 번째 로드를 제외한 업데이트 시의 상태 값을 나타낸다. )

### 이 외 차이점

#### Mutation

- 🌹 `SWR` : `useSWR()`을 통해 얻은 데이터를 클라이언트 사이드에서 변형시켜 업데이트를 해주는 것
- ☀️ `react-query` : post / patch / put / delete를 통해 서버의 상태를 변형시키는 것

#### DevTools

- 🌹 `SWR` : 2.0부터 제공
- ☀️ `react-query` : 자체 제공

#### Lagged Query Data

- 🌹 `SWR` : 기본적으로 지원하지 않아서 추가 코드 구현 필요
- ☀️ `react-query` : 다음 데이터를 불러오기까지 현재 데이터를 표시해준다.

#### Data Optimization

- 🌹 `SWR` : 중복제거, 깊은 비교 등을 통해 불필요한 리렌더링이 발생하는 것을 방지한다.
- ☀️ `react-query` : 쿼리가 업데이트될 때만 컴포넌트가 업데이트된다. 여러 컴포넌트가 같은 쿼리를 사용하는 경우 한 번에 묶어 업데이트해준다.

#### Library Size

- 🌹 `SWR` : MINIFIED + GZIPPED된 값이 대략 4.4kB
- ☀️ `react-query` : MINIFIED + GZIPPED된 값이 대략 13kB

react-query가 지원하는 기능이 많은 만큼 라이브러리 크기가 무겁다.

## 참고

[SWR vs React Query](https://yanggoon.dev/showcase/swr-query)
