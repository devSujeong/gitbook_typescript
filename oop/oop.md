# OOP란

## Imperative and Procedural Programing

명령어와 절차지향적 프로그래밍은 하나의 어플리케이션을 만들 때 필요한 데이터와 함수로 만들어진 프로그래밍입니다. 전역변수로 데이터를 만들고 함수가 그 데이터들을 활용해 순서대로 호출됩니다.

### 단점

* 전역변수로 데이터를 관리하기 때문에 다른 곳에서도 데이터를 업데이트 할 수 있어서 전체를 파악하고 있어야 한다.
* 하나를 수정하면 사이드이펙트가 발생할 가능성이 많고 전체를 파악해야 하므로 확장성이 낮다.

## Object Oriented Programing

Object단위로 프로그래밍 하는 방식입니다. 생산성이 높고 높은 퀄리티로 작성이 가능하고 확장성이 높습니다.

### Object structure

* fields(=properties): 오브젝트 안에 있는 데이터
* methods: 오브젝트 안에 있는 함수

### Class vs Object

| 구분    | Class        | Object              |
| ----- | ------------ | ------------------- |
| 용도    | template     | instance of a class |
| 선언 횟수 | declare once | created many times  |
| 데이터   | no data in   | data in             |

### 4 principles

#### Encapsulation

연관있는 데이터와 함수들을 하나의 오브젝트로 묶는다. 밖에서는 object만 보고 공개된 것만 본다. 내부 상태를 외부에서 변경할 순 없지만 다른 행위로 인해 유도한다.

* public: 외부에도 공개된 데이터
* protected: 상속받은 자식 클래스만 접근 가능한 데이터
* private: 클래스 내부에서만 접근 가능한 데이터

#### Abstraction

추상화를 함으로써 내부 동작원리를 외부에서는 알지 못한다.

Interface를 활용하여 추상화를 잘 구현할 수 있다. class의 property와 methods가 많아도 사용하고 노출할 것만 따로 interface를 만들고, 외부에서 그 interface를 타입으로 지정하면 interface에 지정된 것만 사용하게 강제된다. ㅍㅊ

#### Inhritance

IS-A관계. 

#### polymorphism

다형성.

### Get/Set

```typescript
class User {
    get fullName(): string {
      return `${this.firstName} ${this.lastName}`
    };
    private internalAge = 4;
    get age(): number {
      return this.internalAge;
    }
    set age(num: number) {
      if (num < 0) {
        throw new Error('value of age should be greater than 0');
      }
      this.internalAge = num;
    }

    constructor(private firstName: string, private lastName: string) {
    }
  }

  const user = new User('Steve', 'Jobs');
  user.age = 6; // setter
  console.log(user.age); // getter
```
