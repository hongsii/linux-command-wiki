# which

명령어의 실행 파일 경로를 알려주는 명령어

## 사용법

> which [옵션] 명령어...

| 옵션 | 설명  |
|:----:|-------|
| -a   |  일치하는 실행 파일 경로를 모두 표시 (디폴트는 가장 처음 내용만 표시) |

``` shell
❯ which test
test: shell built-in command
```

여러 파일이 존재하는 경우 

``` shell
❯ which -a test
test: shell built-in command
/bin/test
/bin/test
```
