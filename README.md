---
description: typesciript에 관한 모든 것을 정리합니다.
---

# Typescript

## What is Typescript?

javascript를 감싸고 있는 언어입니다. 동적 타입 언어인 javascript에 type을 정적으로 지정하여 사용할 수 있도록 만든 언어입니다.

> [typescript homepage](https://www.typescriptlang.org/)

## Why should typescript be used?

* 정적 타입이라서 가독성이 높고, 버그를 빨리 발견할 수 있어\(런타임 시기가 아니라 컴파일 시기에 발견\) 안정적으로 코딩을 할 수 있습니다.
* interface, generic, types 등을 사용하여 객체지향 프로그래밍을 더 강력하게 지원합니다. 

## Things to pre-install to use typescript.

* node
* npm install -g typescript \(tsc를 전역으로 사용하기 위해서\)
* npm install -g ts-node \(typescript를 node명령어로 바로 실행하기 위해서\)

## Settings

### watch compile

```bash
tsc -w <file_name>
```

