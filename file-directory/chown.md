# chown

파일/디렉토리의 소유자/그룹을 변경하는 명령어

## 사용법

첫번째 파라미터로 변경할 소유자 및 그룹을 지정하고 두번째 파라머티로는 변경할 파일 또는 디렉토리를 지정한다(한번에 여러 개도 가능)

> chown [옵션] 소유자[:그룹] 파일...
> chown [옵션] :그룹 파일...

| 옵션 | 설명 |
|:----:|------|
| -R   | 디렉토리 및 하위의 대상(파일&디렉토리)의 소유자/그룹까지 변경 (재귀) |
| -f   | 파일의 소유자/그룹 변경 실패시 오류를 출력하지 않음 |
| -v   | 수정된 내용을 상세히 표시 |

#### 현재 파일/디렉토리의 소유자, 그룹 조회

``` bash
# 현재 test.txt의 파일의 소유자는 hong 그룹은 staff

❯ ls -l
----------  1 hong  staff   0 11 12 22:42 test.txt
```

#### 소유자 변경

``` bash
# test.txt 파일의 소유자를 user2로 변경

❯ ls -l
----------  1 hong  admin 0 11 12 22:42 test.txt

❯ chown user2 test.txt

❯ ls -l
----------  1 user2 admin 0 11 12 22:42 test.txt
```

#### 그룹 변경

``` bash
# test.txt 파일의 그룹을 staff로  변경

❯ ls -l
----------  1 user2 admin 0 11 12 22:42 test.txt

❯ chown :staff test.txt

❯ ls -l
----------  1 user2 staff   0 11 12 22:42 test.txt
```

#### 소유자와 그룹을 함께 변경

``` bash
# test.txt 파일의 소유자를 user3, 그룹을 admin으로  변경

❯ ls -l
----------  1 user2 staff 0 11 12 22:42 test.txt

❯ chown user3:admin test.txt

❯ ls -l
----------  1 user3 admin   0 11 12 22:42 test.txt
```

#### 여러개의 파일 한번에 변경

``` bash
# test.txt, test2.txt 파일의 소유자를 hong으로  변경

❯ ls -l
----------  1 user3 admin   0 11 12 22:42 test.txt
----------  1 user3 admin   0 11 12 22:42 test2.txt

❯ chown hong test.txt test2.txt

❯ ls -l
----------  1 hong admin   0 11 12 22:42 test.txt
----------  1 hong admin   0 11 12 22:42 test2.txt
```

#### 하위 대상도 같이 변경

``` bash
# test-dir 및 하위 대상의 소유자를 admin 으로 변경
❯ find test-dir -maxdepth 99 -ls
8599155088        0 drwxr-xr-x    3 hong             staff                  96 11 14 22:55 test-dir
8599155090        0 drwxr-xr-x    3 hong             staff                  96 11 14 23:00 test-dir/test-dir2
8599155324        0 drwxr-xr-x    2 hong             staff                  64 11 14 23:00 test-dir/test-dir2/test-dir3

❯ chown -R admin test-dir

❯ find test-dir -maxdepth 99 -ls
8599155088        0 drwxr-xr-x    3 admin            staff                  96 11 14 22:55 test-dir
8599155090        0 drwxr-xr-x    3 admin            staff                  96 11 14 23:00 test-dir/test-dir2
8599155324        0 drwxr-xr-x    2 admin            staff                  64 11 14 23:00 test-dir/test-dir2/test-dir3
```
