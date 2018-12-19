# 명령어와 함께 사용할 수 있는 특수문자

## 느낌표 !

히스토리에서 실행했던 명령어를 불러올 수 있는 특수문자

* `!히스토리번호` : 히스토리번호와 일치하는 명령어 불러오기

``` shell
❯ history
...
10088  ls
10089  ls -al
10090  mkdir test1

# 히스토리 번호가 10089인 명령어 불러오기
❯ !10089
❯ ls -al
```

* `!-번호` : 마지막으로 실행된 명령어로부터 번호만큼 이전의 명령어 불러오기
    * 마지막 명령어부터 1, 그 다음은 2...

``` shell
❯ history
...
10088  ls
10089  ls -al
10090  mkdir test1

# 마지막 명령어 이전에 실행된 명령어 불러오기
❯ !-2
❯ ls -al
```

* `!!` : 바로 이전에 실행한 명령어 불러오기

``` shell
# 디렉토리 생성 명령어 실행
❯ mkdir test1

# 이전 명령어 불러오기
❯ !!
❯ mkdir test1
```

* 마지막 명령어의 파라미터 가져오기
    * `!^` : 첫번째 파라미터 가져오기
    * `!$` : 마지막 파라미터 가져오기
    * `!*` : 모든 파라미터 가져오기

``` shell
# 디렉토리 생성 명령어 실행
❯ mkdir test1 test2 test3

# 마지막 명령어의 첫번째 파라미터
❯ mkdir !^
❯ mkdir test1

# 마지막 명령어의 모든 파라미터
❯ mkdir !*
❯ mkdir test1 test2 test3
```

* `!명령어` : 마지막으로 실행된 특정 명령어 가져오기

``` shell
❯ history
9000 ls -al test-dir
...
10102  mkdir 123 456 789

# 마지막으로 실행된 ls 가져오기
❯ !ls
❯ ls -al test-dir
```

--------------

## 중괄호 {}

집합을 구성하는 특수문자

* 명령어와 같이 사용하면 집합의 각 요소마다 동일한 명령어를 실행

``` shell
# 동일한 접두사 test를 가지는 여러 개의 폴더 생성
❯ mkdir test{1,2,3}
test1 test2 test3

# ..를 이용해 시퀀스 형태의 집합으로도 구성할 수 있음
❯ mkdir test{1..3}
test1 test2 test3

# 알파벳으로도 가능
❯ mkdir test{a..e}
testa testb testc testd teste

# 여러 문자열의 집합도 가능
❯ mkdir test{set1,other}
testset1 testother
```


