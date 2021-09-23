# Types

## 타입 정의 방법

`:`를 이용하여 타입 정의: Type Annotation

## Javascript Basic Types

```typescript
const num: number = -6;
const str: string = 'hello';
let str1: 'hi' | 'hello' | 'hey' = 'hi';
const boal: boolean = false;
let age: number | undefined;
let person2: string | null;
let obj: object; // 선언은 가능하지만 이는 모든 객체가 다 들어올 수 있어서 효용성이 없다.
let person: {name: string, age: number} = {
	name: 'Crystal',
	age: 20
};
let arr: number[] = [1,2,3];
let arr: Array<number> = [1,2,3];
```

## Typescript Types

```typescript
// unknown: 무슨 타입이 오는지 나는 모른다. 즉, 모든 타입이 올 수 있어 효용성 없음
let notSure: unknown = 0;

// any: 어떤 타입이든 담을 수 있다. 이 역시 모든 타입이 올 수 있어 효용성 없음
let anything: any = 0;

// void: 함수에서 아무 것도 리턴하지 않음을 의미
 function print(): void {
 console.log('hello');
 return;
}
let unuseful: void = undefined; // 의미가 없는 코드..

// never: 함수에서 리턴을 선언하지 않음을 의미(함수가 끝나지 않음을 의미)
 function throwError(message: string): never {
  // message -> server (log)
  // 1) throw new Error(message);
  // 2) while (true) {}
}
```



### Tuple

튜플은 배열의 길이가 고정되고 각 요소의 타입이 지정되어 있는 배열 형식입니다.

```text
let arr: [string, number] = ['hi', 10];
```

### Enum

이넘은 특정 값\(상수\)들의 집합입니다.

.이나 인덱스 번호로 접근이 가능하며, 인덱스를 사용자 편의로 변경도 가능합니다.

```text
enum Avengers { Capt = 2, IronMan, Thor }
let hero: Avengers = Avengers.Capt;
let hero2: Avengers = Avenger[2] // Capt
```

