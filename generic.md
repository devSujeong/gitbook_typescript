# Generic

## Generic이란?

어떤 타입이 올 지 미리 알 수 없는 상황에서 공간을 만들어두고, 받은 타입으로 타입을 대체하는 문법입니다.

### function

```typescript
function checkNotNull<T>(arg: T | null): T {
    if (arg == null) {
      throw new Error('not valid number!');
    }
    return arg;
  }
  const number = checkNotNull(123);
const boal: boolean = checkNotNull(true);
```

