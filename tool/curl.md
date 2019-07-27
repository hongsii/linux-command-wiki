# curl

서버로 데이터를 보내거나 받을 수 있는 명령

## 옵션

| 옵션명 | 설명        |
|:-------|-------------| 
| -H     | Request Header 설정 |
| -X     | Request Method 설정 [default : GET] (GET, POST, PUT..)  |
| -d     | Request Body 설정 |
| -i     | Response Header 출력 |

## HTTP 요청

### 다운로드

응답을 콘솔에 출력

``` shell
curl https://www.google.com 
```

`curl-desc.md` 라는 파일로 저장

``` shell
curl -o curl-desc.md https://raw.githubusercontent.com/hongsii/linux-command-wiki/master/tool/curl.md
```

### 요청 보내기

GET 요청 보내기

``` shell
curl -X GET https://www.google.com
curl -X GET https://www.google.com/search?q=google
```

POST 요청 보내기

* `-H` : 요청 헤더를 설정
* `-d` : 바디로 보낼 데이터를 설정
* 여러 줄로 사용할 경우 `\` 를 마지막에 붙여줘야 한다.

``` shell
curl -X POST 'https://www.test-url.co.kr' \
    -H 'AUthorization: test-token' \
    -d id=1 \
    -d type=test
```
