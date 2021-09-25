# Directive

## readonly

해당 배열, 객체를 수정할 수 없고 오직 읽을 수만 있게 함.

* 배열은 표현 방법이 `string[]`, `Array<string>` 2가지 이지만, `readonly`를 사용할 때는 `string[]` 표현식만 가능하다.

```typescript
function printArray(fruits: readonly string[]) {}
```

## \| \(Union Type\)

또는\(or\) 이라는 의미로 사용함.

```typescript
type Direction = 'left' | 'right' | 'up' | 'down';
```

## in

우항에 있는 타입의 속성을 가지고 있는지 확인

```typescript
type SuccessState = {
  response: {
    body: string;
  };
};
type FailState = {
  reason: string;
};
type LoginState = SuccessState | FailState;


function printLoginState(state: LoginState) {
  if ('response' in state) {
    console.log(`🎉 ${state.response.body}`);
  } else {
    console.log(`😭 ${state.reason}`);
  }
}
```

