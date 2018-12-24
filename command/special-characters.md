# 명령어와 함께 사용할 수 있는 특수문자

* 느낌표 !
* 중괄호 {}
* 물음표 ?
* 별표 *
* 파이프 |
* 대괄호 []

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

## 물음표 ?

물음표 위치에 문자 하나를 일치시킬 수 있는 와일드카드 문자

``` shell
# test1, test2, testa, testabc 라는 디렉토리가 존재
# test로 시작하는 5개의 문자로 구성된 대상을 출력
❯ ls -al test?
test1:
...

test2:
...

test3:
...

testa:
...

# 3개의 문자로 구성 대상을 출력
❯ ls -al ???
```

## 별표(애스터리스크) *

0개 이상의 문자를 일치시킬 수 있는 와일드카드 문자

``` shell
# test1, test2, testa, testabc 라는 디렉토리가 존재
# test로 시작하는 모든 대상 출력
❯ ls -al test*
test1:
...
test2:
...
test3:
...
testa:
...
testabc:
...

# 현재 디렉토리의 모든 대상 출력
❯ ls -al *
```

## 파이프 |

표준 출력을 다른 프로세스의 표준 입력으로 보내는 특수문자

``` shell
# ps 명령어의 표준 출력을 grep 명령어의 표준 입력으로 보내 "java" 문자가 들어간 프로세스를 검색
❯ ps -ef | grep java
```

## 대문자 []

{}와 비슷한 기능으로 집합을 구성하는 특수문자

``` shell
# 접두사가 test이며, A부터 C까지 일치하는 파일 모두 출력
❯ ls test[A-C]
testA testB testC

# 접두사가 test인 A 또는 C와 일치하는 파일 모두 출력
❯ ls test[AC]
testA testC
```
