# touch

크기가 0인 파일을 생성하거나 파일의 날짜를 변경할 수 있는 명령어

## 사용법

``` shell
❯ touch [옵션] 파일...
```

| 옵션   | 설명 |
|:------|------|
| -A [-][[hh]mm]SS          | 파일의 시간을 특정한 값으로 더하거나 빼서 조절할 수 있음<br/> `-` : 시간을 뺄 때 사용  <br/> `hh` : 시 (00~99) <br/> `mm` : 분 (00~59) <br/> `SS` : 초 (00-59)  |
| -c                        | 파일이 존재하면 파일의 시간을 현재시간으로 변경 (존재하지 않으면 아무런 동작X) |
| -a                        | 파일의 Access time (atime)을 현재시간으로 변경 |
| -m                        | 파일의 Modification time (mtime)을 현재시간으로 변경 |
| -r src-file dst-file      | dst-file의 시간을 src-file의 시간과 동일하게 변경 |
| -t [[CC]YY]MMDDhhmm[.SS]] | 날짜 포맷으로 Access/Modification time을 변경 <br/> `CC` : 연도의 앞의 2개 숫자 <br/> `YY` : 연도의 뒤의 2개 숫자 (CC를 생략하면 YY가 69~99 사이일 때, 19로 설정 그 외는 20으로 설정) <br/> `MM` : 월 (01~12) <br/> `DD` : 일 (01~31) </br> `hh` : 시 (00~23) </br> `mm` : 분 (00~59) </br> `SS` : 초 (00~61) |

### 파일 생성

``` shell
# test.txt 파일 생성
❯ touch test.txt
❯ ls -l
-rw-r--r--   1 hong  staff     0  1 31 23:20 test.txt
```

### 파일 날짜 변경

``` shell
# test.txt 파일이 존재하면 현재시간으로 시간 변경
❯ touch -c test.txt
❯ ls -l
-rw-r--r--   1 hong  staff     0  1 31 23:23 test.txt
```

### 파일의 Modification 타임만 변경

``` shell
❯ touch -m test.txt
# ls -l에 표시되는 시간은 Modification time
❯ ls -l
-rw-r--r--  1 hong  staff  0  1 31 23:25 test.txt
# ls -ul에 표시되는 시간은 Access time
❯ ls -ul
-rw-r--r--  1 hong  staff  0  1 31 23:23 test.txt
```

### 날짜 포맷으로 파일 날짜 변경

``` shell
❯ ls -l
-rw-r--r--  1 hong  staff  0  1 31 23:25 test.txt
# test.txt의 시간을 1월 5일 23시 00분으로 변경
❯ touch -t 01052300 test.txt
❯ ls -l
-rw-r--r--   1 hong  staff     0  1  5 23:00 test.txt
```
