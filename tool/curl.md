# curl

서버로 데이터를 보내거나 받을 수 있는 명령

* 지원하는 프로토콜 : DICT, FILE, FTP, FTPS, GOPHER, HTTP, HTTPS, IMAP, IMAPS, LDAP, LDAPS, POP3, POP3S, RTMP, RTSP, SCP, SFTP, SMB, SMBS, SMTP, SMTPS, TELNET and TFTP


## 옵션

| 옵션명 | 설명        |
|:-------|-------------| 
| -H     | Request Header 설정 |
| -X     | Request Method 설정 [default : GET] (GET, POST, PUT..)  |
| -d     | Request Body 설정 |
| -i     | Response Header 출력 |

## HTTP

### 다운로드

응답을 콘솔에 출력

``` shell
curl https://www.google.com 
```

`curl-desc.md` 라는 파일로 저장

``` shell
curl -o curl-desc.md https://raw.githubusercontent.com/hongsii/linux-command-wiki/master/tool/curl.md
```

