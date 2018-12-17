# cd

디렉토리를 이동하는 명령어

## 사용법

``` shell
cd [디렉토리 경로]
```

``` shell
# /Users 폴더로 이동
❯ cd /Users 

# 상위 디렉토리로 이동
# 현재 경로가 /Users/Programming이라면 /Users로 이동
❯ cd ..

# 사용자 홈 디렉토리로 이동
❯ cd ~
❯ cd $HOME
❯ cd

# 특정 사용자 홈 디렉토리로 이동
❯ cd ~사용자 계정
```

특정 변수에 저장된 디렉토리로 이동도 할 수 있음

``` shell
# 현재 경로 확인
❯ pwd
/Users/hong/Programming
# 변수에 경로 저장
❯ PG_PATH=/Users/hong/Programming
# 이동
❯ cd $PG_PATH
```

이전 디렉토리로 돌아가고 싶다면 `-` 사용

``` shell
# 이전 디렉토리로 이동
❯ pwd
/Users/hong/Programming/linux-command-wiki
# 다른 경로로 이동
❯ cd /Users
# 이전 디렉토리로 이동
❯ cd -
❯ pwd
/Users/hong/Programming/linux-command-wiki
```

#### 디렉토리 생성 후, 이동

디렉토리 생성 명령어(mkdir)과 조합하면 하나의 행에서 폴더 생성 후, 이동까지 가능

``` shell
# $_는 이전 명령어의 마지막 파라미터를 반환
❯ mkdir my-test-dir && cd $_
```

