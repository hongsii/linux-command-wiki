# sort

텍스트 데이터 또는 라인, 바이너리 파일을 정렬하는 명령어

## 사용법

``` shell
sort [옵션] [file...]
```

| 옵션                 | 설명 |
|----------------------|------|
| -f, --ignore-case    | 모든 소문자를 대문자로 변경해서 정렬 (대소문자 상관없이 정렬) |
| -u, --unique         | 중복 제거 |
| -r, --reverse        | 역순으로 정렬 |
| -R, --random-sort, --sort=random | 랜덤으로 정렬 |
| -k field1.. --key=field... | 필드 포지션을 기준으로 정렬 |
| -t char, --field-separator=char | 필드 구분자 설정 |
| -n | 숫자 정렬 |


### 파일 정렬

``` shell
# Number.txt 정렬하기
$ sort Number.txt
# 또는
$ cat Number.txt | sort
```

### ls 결과 정렬

``` shell
# 파일 크기 순으로 정렬하기 (파일 크기가 공백을 기준으로 5번쨰 필드에 위치)
$ ls -al | sort -k5
```
