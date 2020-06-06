# jq

JSON 포맷 처리를 할 수 있는 명령어

## 설치

```bash
$ brew install jq # OSX
$ apt-get install jq # Debian / Ubuntu
```

## 사용법

```bash
jq [options...] filter [files...]
```

기본적으로 보여 주기 좋게 정렬하려면 필터에 `'.'` 을 입력하면 된다. (기본값이라 생략 가능)

```bash
$ jq '.' test.json
{
  "foo": 1
}
```

파일이 아닌 CLI의 입력을 통해서도 사용할 수 있다.

```bash

$ jq '.'
# 명령어 입력 시 JSON 입력 받음
{"foo":1}
# 입력값을 파싱해서 보기 좋은 형태로 출력
{
  "foo": 1
}
```

파이프 연산자로 다른 프로세스의 출력값을 사용할 수 있다.

```bash
$ echo '{"foo":1}' | jq
{
  "foo": 1
}
```

## 필터

jq는 보기 좋은 형태로 출력하는 것 외에도 유용한 기능을 제공한다.

### 속성

출력할 속성을 입력하면 값을 조회할 수 있다.

```bash
$ echo '{"foo":1}' | jq '.foo'
1

$ echo '{ "foo": { "bar" : 2 } }' | jq '.foo.bar'
2
```

### 배열

`[index]` 을 사용하면 배열 안의 값을 조회할 수 있다.

```bash
$ echo '[1,2,3,4]' | jq '.[2]'
3
$ echo '{"arr":[1,2,3,4]}' | jq '.arr[2]'
3
```

index를 생략하면 배열 안의 모든 값을 조회할 수 있다.

```bash
$ echo '[1,2,3,4]' | jq '.[]'
1
2
3
4
```
