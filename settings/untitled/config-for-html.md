# config for html

## 1 개의 파일 watch모드

```bash
tsc <file name> -w
```

## 여러 개의 파일 WATCH 모드&#x20;

```bash
tsc --init // tsconfig 생
tsc -w // tsconfig가 있는 모든 TS파일 Watch
```

### tsconfig.json

```json
{
    "compilerOptions": {
        "outDir": "./build", // typescript를 컴파일하여 내보내는 JS파일 위
        "rootDir": "./src", // root가 어디냐에 따라 빌드 파일 구조가 달라지므로 이를 막기 위해 최상단 DIRECTORY를 정해줌.
    },
    "exclude": ["./src/dev.ts"], // 컴파일 제외 파일
    "include": ["./src/dev.ts"] // 이 애들만 컴파일함
}
```

tsc로 실행.
