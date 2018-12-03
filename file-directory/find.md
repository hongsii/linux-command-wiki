# find

디렉토리를 검색해 조건에 맞는 파일을 찾는 명령어

## 사용법

``` shell
find [검색 경로] [옵션] [표현식]
```

| 옵션         | 설명 |
|:------------:|------|
| -name 파일명 | 지정된 이름의 파일을 찾음 |
| -user 유저명 | 유저가 소유한 파일을 찾음 |
| -print       | 표준출력으로 검색된 파일을 출력 (절대경로) |
| -type 형식   | 지정된 형식의 파일을 찾음 <br/> -b : 블록파일 <br/> -c : 문자 <br/> -d : 디렉토리 <br/> -f : 파일 <br/> -l : 링크파일 <br/> -s : 소켓 |
| -exec command {} \; | 찾은 파일에 대해 명령어를 실행 |
| -ok command {} \; | 실행 여부를 확인한 후, 명령어를 실행 (y : 실행 / n : 미실행) |
| -depth n    | n번째 depth에 있는 파일 검색 |
| -maxdepth n | 0~n번째 depth까지의 파일 검색 |
| -mindepth n | n번째 depth부터 파일 검색 |

#### 이름으로 파일 찾기

``` shell
# 홈 경로(~) 아래의 모든 'test.txt' 파일 검색
❯ find ~ -name test.txt

# 홈 경로(~) 아래의 'test'로 시작하는 텍스트 파일 검색
❯ find ~ -name "test*.txt"
```

#### 현재 경로 아래의 모든 파일 찾기

``` shell
❯ find .
```

#### 현재 경로 아래의 모든 디렉토리 찾기

`-type` 옵션을 사용하면 원하는 타입의 파일만 찾일 수 있음

``` shell
❯ find . -type d
```

#### 찾은 파일에 대해 추가 명령어 실행

`-exec` 옵션을 사용하면 찾은 파일에 원하는 명령어를 실행할 수 있음

* 명령어는 `\;` 으로 끝나야함
* `{}`는 검색된 파일을 뜻함

``` shell
# 현재 경로 아래의 'test'로 시작하는 파일 또는 디렉토리 삭제
❯ find . -name "test*" -exec rm -rf {} \;
```

#### 원하는 depth의 파일 찾기

입력한 검색 경로부터 0 depth이며, 하위로 내려갈 때마다 1 depth씩 증가

``` shell
# home 디렉토리 아래에 다음과 같은 depth의 디렉토리와 파일이 존재
home
 - dir_depth1
    - dir_depth2
       - dir_depth3
          - dir_depth4
          - depth4.txt
    - depth1.txt
 - depth1.txt

# home 디렉토리 내의 2번째 depth의 파일 검색
❯ find home -depth 2
/home/dir_depth1/dir_depth2
/home/dir_depth1/depth2.txt

# home 디렉토리 내의 2번째 depth까지의 파일 검색
❯ find home -maxdepth 2
/home
/home/dir_depth1
/home/depth1.txt
/home/dir_depth1/dir_depth2
/home/dir_depth1/depth2.txt

# home 디렉토리 내의 2번째 depth부터 파일 검색
❯ find home -mindepth 2
/home/dir_depth1/dir_depth2
/home/dir_depth1/depth2.txt
/home/dir_depth1/dir_depth2/dir_depth3
/home/dir_depth1/depth2.txt/dir_depth3/dir_depth4
/home/dir_depth1/depth2.txt/dir_depth3/depth4.txt
```
