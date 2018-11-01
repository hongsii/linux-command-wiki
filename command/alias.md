# alias

자주 사용하는 명령어를 별칭으로 설정해 간단하게 실행할 수 있게 해주는 명령어

> alias 별칭[=명령어]


## 사용법

alias 설정

[![alias](https://asciinema.org/a/209553.png)](https://asciinema.org/a/209553)

``` shell
❯ alias wiki='cd ~/Programming/linux-command-wiki/alias'
```

설정된 alias 확인

``` shell
❯ alias wiki
wiki=/Users/hong/Programming/linux-command-wiki/alias
```

설정한 alias를 터미널에 입력하면  사용할 수 있음

``` shell
❯ wiki
```

현재 시스템에 설정된 모든 alias를 조회 (기본적으로 시스템에서 설정된 alias도 존재함)

``` shell
❯ alias
-='cd -'
...
md='mkdir -p'
wiki=/Users/hong/Programming/linux-command-wiki/alias
```

alias를 해제하고 싶다면 `unalias` 사용

``` shell
unalias wiki
```

alias 명령어로 별칭을 설정하면 **현재 사용 중인 shell만 적용되기 때문에 shell이 종료되면 alias도 해제**됨  
alias를 영구적으로 설정하고 싶다면 아래와 같이 적용

1. 특정 계정에만 적용
    * 사용자의 홈폴더(~)에 현재 사용 중인  shell의 profile에 alias 설정

2. 모든 사용자 계정에 적용
    * /etc/porfile에 alias 설정

``` shell
# 1) .bash_profile을 열어 alias를 설정하고 저장하면 로그인시 마다 alias가 적용되어 있음
❯ vim ~/.bash_profile 
원하는 alias 설정
❯ source ~/.bash_profile # 즉시 적용

# 모든 사용자에게 적용하고 싶다면 /etc/profile을 열어 1)과 동일한 방법으로 설정
❯ sudo vim /etc/profile
원하는 alias 설정
❯ source /etc/profile
```
