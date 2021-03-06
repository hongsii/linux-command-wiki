# ls

디렉토리의 내용을 출력하는 명령어

## 사용법

``` shell
ls [옵션] [파일...]
```

| 옵션 | 설명 |
|:-----:|------|
| -a   | 현재 디렉토리의 모든 내용 표시 (점 `.` 으로 시작하는 숨김 파일까지 표시) |
| -l   | 상세 정보와 함께 표시 |
| -o   | 상세 정보와 함께 표시 (그룹만 생략) |
| -h   | `-l` 옵션 사용시 나타나는 바이트를 읽기 쉬운 단위로 표시 (B, K, M, G, T, P) | 
| -T   | `-l` 옵션 사용시 전체 시간으로 표시 |
| -u   | 정렬 또는 상세 정보 표시할 때, `마지막 수정일` 대신에 `마지막 접근일` 사용 |
| -U   | 정렬 또는 상세 정보 표시할 때, `마지막 수정일` 대신에 `생성일` 사용 |
| -G   | 색깔을 사용해 내용 표시 |
| -R   | 서브 디렉토리의 내용까지 표시 |
| -S   | 파일 크기순으로 정렬 |
| -t   | 마지막 수정일순으로 정렬 |
| -r   | 정렬 결과를 역순으로 표시 |


### 상세 내용 (Long Format)

`-l` 옵션 사용시 추가로 조회되는 내용은 `파일 모드`, `하드링크 수`, `소유자`, `그룹`, `파일의 크기`, `마지막 수정일`, `파일명` 순으로 표시된다.

``` shell
$ ls -al

drwxr-xr-x   3 hongsii staff    96  5 12 22:32 .
drwxr-xr-x+ 51 hongsii staff  1632  5 12 22:32 ..
-rw-r--r--   1 hongsii staff    32  5 12 22:32 mytext.md
```
