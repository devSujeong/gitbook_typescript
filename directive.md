# Directive

## readonly

해당 배열, 객체를 수정할 수 없고 오직 읽을 수만 있게 함.

* 배열은 표현 방법이 `string[]`, `Array<string>` 2가지 이지만, `readonly`를 사용할 때는 `string[]` 표현식만 가능하다.

```typescript
function printArray(fruits: readonly string[]) {}
```

## \| \(Union Type\)

a 또는 b 또는 c 또는 d가 올 수 있다는 뜻.

```typescript
type Direction = 'left' | 'right' | 'up' | 'down';
```

## & \(Intersection type\)

모든 것을 다 합한 의미로 사용 a도 b도 c도 d도 다 있어야 한다는  

```typescript
type Student = {
  name: string;
  score: number;
};

type Worker = {
  empolyeeId: number;
  work: () => void;
};

function internWork(person: Student & Worker) {
  console.log(person.name, person.empolyeeId, person.work());
}

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

## as \(Type Assertion\)

타입을 명시적으로 지정해 줌

```typescript
function jsStrFunc(): any {
    return 2;
}
const result = jsStrFunc();
console.log((result as string).length);
console.log((<string>result).length);
```

## !

절대적으로 값이 있음을 확신할 때 표현

```typescript
function findNumbers(): number[] | undefined {
    return undefined;
  }
  const numbers = findNumbers()!;
  // or
  numbers!.push(2);
```

