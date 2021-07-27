# Error Handling

## explicit-module-boundary-types

명백하게 리턴값을 정의하라는 뜻입니다.  
예시1\) 리액트의 경우 ReactElement를 반환한다고 컴포넌트 함수에 명시하였습니다.

```javascript
// libraries
import type { AppProps } from 'next/app';
import { ReactElement } from 'react';

function MyApp({ Component, pageProps }: AppProps): ReactElement {
  return <Component {...pageProps} />;
}
export default MyApp;
```

## Unknown compiler options include & exclude

include, exclude를 compilerOptions에 넣었을 때 발생

## Specified 'include' paths were '\["_\*/_"\]' and 'exclude' paths were '\[\]'

tsconfig파일과 같은 경로에 .ts파일이 하나도 없어서 생긴 문제.

## ts2304: cannot find name ~

tsx 파일을 ts로 선언했을 때 jsx를 알지 못

