---
title:  "AWS EC2 창 닫아도 꺼지지 않게 서버 유지"
excerpt: "AWS EC2, GCP VM Instance, Azure VM ware Don't Sleep "
header:
  teaser: /assets/images/bio-photo-keyboard-teaser.jpg

categories:
  - 개발
tags:
  - cloud
  - AWS
  - GCP
  - Azure
last_modified_at: 2020-10-15T13:50:00-00:00
---


## 1. 왜 서버 켜놨는데 터미널 닫으면 꺼질까?

AWS EC2, GCP VM Instance, Azure VMware를 사용할 때 커맨드 창을 끄게 되면 같이 서버도 닫히는 현상이 있다.

이유는 아마 백그라운드에 돌지 않아서인 거 같다.

> nohup 은 “no hangups” 라는 의미로, 리눅스/유닉스에서 쉘 스크립트파일을 데몬 형태로 실행시키는 명령어라고 한다.


## 2. 안꺼지게 명령어 입력! 

### Python3 예제
```
nohup python3 main.py &
```


### React 등 사용예제
```
nohup npm start &
```

이런식으로 응용을 하면 커맨드 창을 닫아도 백그라운드에 서비스가 유지 된다.

nohup.out이라는 로그파일이 생성되는데 여기서 로그 확인 가능




***



## 3. 그럼 끄는 방법은?

```
ps -ef | grep 쉘스크립트파일명
```

nohup 종료방법은 다음 명령어를 통해 PID를 찾고

```
kill -9 PID
```

kill 명령어를 통해 프로세스를 죽여주면 된다.


- 끝 -