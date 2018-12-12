# basename

파일명[또는 경로를 포함한 파일명] 을 파라미터로 받아 파일명만 추출할 수 있는 명령어

## 사용법

``` shell
basename [파일(또는 경로가 포함된 파일)] [확장자]
```

``` shell
# 1번째 파라미터로 받은 값에서 확장자가 포함된 파일명 반환
# 홈폴더에 존재하는 test.sh의 파일명만 추출
❯ ls ~/test.sh
/Users/hong/test.sh

❯ basename ~/test.sh
test.sh

# 2번째 파라미터로 받은 값과 동일한 확장자가 있다면 확장자가 제거된 파일명 반환
❯ basename ~/test.sh .sh
test
```
