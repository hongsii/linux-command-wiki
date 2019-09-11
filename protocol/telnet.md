# telnet

네트워크 프로토콜로 원격 서버에 접속할 때 사용하는 명령어
(보안 문제로 telnet 보다는 SSH를 사용하는 걸 추천)

## 사용법

```
telnet Host [Port]
```

* `Host` : IP 또는 Domain
* `Port` 를 생략하면 telnet 기본 포트(23)으로 접속

``` shell
telnet google.com 80
```

접속 성공 시 아래와 같이 표시

``` shell
Trying 172.217.25.238...
Connected to google.com.
Escape character is '^]'.
```
