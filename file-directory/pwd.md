# pwd

현재 디렉토리 경로를 출력하는 명령어

## 사용법

``` shell
pwd [옵션]
```

| 옵션 	| 설명 	|
|:----:	|:------|
| -L 	| 현재 디렉토리가 위치한 논리적 경로 표시 |
| -P    | 심볼릭 링크 디렉토리는 참조 중인 디렉토리의 경로가 표시 |

* 옵션을 지정하지 않는 경우 OS마다 정해진 옵션을 기본으로 사용
    * ubuntu에서는 `-P` 옵션이 적용
    * Mac에서는 `-L` 옵션이 적용됨

``` shell
# 아래와 같이 home 디렉토리 안에 'test' 디렉토리와 이 디렉토리의 심볼릭 링크인 'test-link'가 존재
❯ ls -l
drwxr-xr-x    3 hong  staff      96  2 18 20:21 test
lrwxr-xr-x    1 hong  staff       4  2 18 20:21 test-link -> test
```

`-L` 옵션을 사용하면 현재 심볼릭 링크 디렉토리가 위치한 경로가 표시됨

``` shell
❯ cd test-link
❯ pwd -L
/home/test-link
```

`-P` 옵션을 사용하면 심볼릭 링크가 참조 중인 실제 디렉토리의 경로가 표시됨

``` shell
❯ cd test-link
❯ pwd -P
/home/test
```
