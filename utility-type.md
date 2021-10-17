# Utility Type

## Index Type

\[]를 사용하면 index Type을 만들 수 있습니다. computed property처럼 계산된 값을 사용할 수 있습니다.

```typescript
type Animal = {
  name: string;
  age: number;
  gender: 'male' | 'female';
};

type Name = Animal['name']; // string
const text: Name = 'hello';
```

## Mapped Type

type의 key에 index type을 사용하면 전달받은 타입의 모든 요소를 한바퀴 순환합니다.

* \[P in keyof T]: 제레릭 T의 키를 순회
* T\[P]: P를 키로 한 T의 value property

```typescript
type Nullable<T> = { [P in keyof T]: T[P] | null };
const obj2: Nullable<Video> = {
  title: 'hi',
  author: null,
};

type Proxy<T> = {
  get(): T;
  set(value: T): void;
};

type Proxify<T> = {
  [P in keyof T]: Proxy<T[P]>;
};
```

## Conditinal Type

조건을 달아서 타입을 지정할 수 있습니다. 3항 연사자 사용.

```typescript
type Check<T> = T extends string ? boolean : number;
type Type = Check<string>; // boolean
```

## ReadOnly

수정이 불가능한 타입을 만듦.

```typescript
type ToDo = {
  title: string;
  description: string;
};

function display(todo: Readonly<ToDo>) {
  // todo.title = 'jaja';
}
```

## Partial Type

옵셔널 프로퍼티로 만듦

```typescript
type ToDo = {
    title: string;
    description: string;
    label: string;
    priority: 'high' | 'low';
};

function updateTodo(todo: ToDo, fieldsToUpdate: Partial<ToDo>): ToDo {
    return { ...todo, ...fieldsToUpdate };
}
```

## Pick Type

전달받은 타입의 일부 요소들만 사용

```typescript
type Video = {
    id: string;
    title: string;
    url: string;
    data: string;
};
type VideoMetadata = Pick<Video, 'id' | 'title'>;

function getVideoMetadata(id: string): VideoMetadata {
    return {
      id: id,
      title: 'title',
    };
}
```

## Omit Type

pick type의 반대로 일부 요소를 제외하고 사용

```typescript
type Video = {
    id: string;
    title: string;
    url: string;
    data: string;
};
type VideoMetadata = Omit<Video, 'url' | 'data'>;

function getVideoMetadata(id: string): VideoMetadata {
    return {
      id: id,
      title: 'title',
    };
}
```

## Record

첫 번째 제네릭이 키, 두 번째 제네릭이 밸류가 되어서 새로운 타입을 조합함.

```typescript
type PageInfo = {
  title: string;
};
type Page = 'home' | 'about' | 'contact';

const nav: Record<Page, PageInfo> = {
  home: { title: 'Home' },
  about: { title: 'About' },
  contact: { title: 'Contact' },
};
```

## Capitalize, Uppercase, Lowercase

타입 값들의 영문법 표기법을 바꿔줌. 백단에서 데이터를 통일성없이 주거나 할 때 맞추기에 용이함.
