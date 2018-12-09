# head

파일의 첫 부분을 출력하는 명령어

## 사용법

``` shell
head [옵션] [파일명]
```

* MacOS에서는 `-숫자`, `-n`, `-c` 옵션만 가능

| 옵션  | 설명 |
|:-----:|------|
| -줄수     | 원하는 줄수만큼 출력 (default: 10줄) |
| -n 줄수   | 원하는 줄수만큼 출력 (-숫자와 동일)  |
| -c bytes  | 원하는 크기만큼 출력 (b = 512bytes, k = kb, m = mb) |
| -q        | 출력시 파일명을 표시하지 않음        |
| -v        | 출력하는 파일명 표시                 |

#### 원하는 줄수만큼 출력

``` shell
# test.txt파일의 처음 10줄 출력
❯ head test.txt

# 처음부터 지정된 줄수만큼 표시
❯ head -10 test.txt
❯ head -n 10 test.txt
```

#### 일정 크기만큼 출력

``` shell
# test.txt파일의 처음부터 100bytes만큼 출력
❯ head -c 100 test.txt
```
