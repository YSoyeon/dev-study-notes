# 유용한 console API

### console.table

객체를 테이블 형태로 출력해줘서 가독성이 좋음

### console.assert

주어진 조건이 거짓인 경우 콘솔에 오류 메시지 출력

```js
console.assert(number % 2 === 0, { number, errorMsg });
```

### console.count

불필요한 리렌더링을 줄이고자 할 때 사용하기 유용하다.

```js
console.count(); // 1
```

### console.countReset

`console.count()` 초기화

```js
console.countReset();
```

### console.time(), console.timeEnd()

console.time()은 작업 소요 시간을 추적하는 데 사용할 수있는 타이머를 시작 및 종료
