---
description: Next.js에서 typescript를 설치하는 방법을 알아봅시다.
---

# Install in Next.js

## Install

### Automatic install

Next.js에서 제공하는 typescript version template. recommanded

```bash
npx create-react-app my-app --template typescript
```

### Manual install

* typescript: typescript 설치
* @types/react: react의 type 지정 파일
* @typescript-eslint/eslint-plugin : eslint에서 typescript 옵션 사용
* @typescript-eslint/parser: eslint에서 typescript parser 사용

```bash
yarn add --dev typescript @types/react @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

## eslint + typescript

```javascript
// .eslintrc.js
module.exports = {
  env: {
    node: true,
    browser: true,
    es2021: true,
  },
  extends: [
    'eslint:recommended',
    'next',
    'next/core-web-vitals',
    'plugin:react/recommended',
    'plugin:@typescript-eslint/recommended',
    'prettier',
  ],
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 12,
    sourceType: 'module',
  },
  plugins: ['react', '@typescript-eslint', 'react-hooks', 'import', 'jsx-a11y', 'prettier'],
  rules: {
    'react/react-in-jsx-scope': 'off',
    'react-hooks/rules-of-hooks': 'error', // Checks rules of Hooks
    'react-hooks/exhaustive-deps': 'error', // Checks effect dependencies
    'react/display-name': 'off',
    '@typescript-eslint/no-empty-function': 'off',
    '@next/next/no-img-element': 'off',
  },
};

```

## Typescript environment setting

모든 typescript setting 관련 내용을 다 담아 tsconfig.json 생성

```bash
yarn run tsc --init # tsconfig.json 만드는 명령어1
npx typescript --init # tsconfig.json 만드는 명령어2
```

### tsconfig.json

```javascript
{
	"compilerOptions": {
		"allowJs": true, // js 파일도 허용
		"checkJs": true, // @ts-check 역할
		"noImplicitAny": true, // any 타입으로 암시한 표현식과 선언에 오류를 발생시킵니다. any를 쓰더라도 명시를 하라!
		"outDir": "./", // 컴파일 결과물을 어디에 놓을지 설정
		"target": "ES5", // 컴파일할 때 javascript 버전 설정.
		"moduleResolution": "node", // promise할 때 필요하다고 함.
		"lib": ["ES2015", "DOM", "DOM.Iterable"] // lib를 정의하지 않으면 target의 버전을 기준으로 컴파일할 때 사용한다. 
		"baseUrl": ".", // 절대경로를 사용할 수 있습니다. 파일 경로의 default를 지정해 줍니다.
	},
	"include": ["./src/**/*"] // 어디서 읽어와서 컴파일 할 건지
	"exclude": ["node_modules"] // 제외할 대상
	...
}
```

