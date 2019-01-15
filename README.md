# lerna-test
monorepo관련 플러그인 lerna repository 관련 테스트입니다.
관련된 내용은 [root에서의 package사용](https://github.com/trustyoo86/my-conference/blob/master/references/lerna-root.md) 에서도 확인 가능합니다.

## references
[lerna github](https://github.com/lerna/lerna)

## 사용법
lerna가 전역에 설치되어 있어야 합니다.

```bash
npm install -g lerna
```

### bootstrap
모든 package들의 모듈을 설치하기 위해서, bootstrap 명령어를 실행합니다.

```bash
lerna bootstrap
```

### package간 dependencies 주입
package.json에 해당 package에 대한 의존성을 생성합니다.

```js
# packages/pac-1/pakcage.json
{
    "name": "pac-1",
    "version": "0.0.1"
}
  
# packages/pac-2/package.json
{
    "dependencies": {
        "pac-1": "github:user-name/pac-1#0.0.1"
        #or
        "pac-2": "file:../pac-1"
    }
}
```

lerna bootstrap을 재 실행합니다. (root)

```bash
lerna bootstrap
```

### root에서 dependencies 주입
[root에서의 package사용](https://github.com/trustyoo86/my-conference/blob/master/references/lerna-root.md)에서 확인 가능합니다.