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



