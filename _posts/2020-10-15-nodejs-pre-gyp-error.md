---
title:  "node_modules/grpc/node_modules/.bin/node-pre-gyp" "install" "--fallback-to-build" "--library=static_library" 에러 해결 방법"
excerpt: "node_modules/grpc/node_modules/.bin/node-pre-gyp" "install" "--fallback-to-build" "--library=static_library  에러 발생시 해결 방법 중 하나"
toc: true
toc_sticky: true
header:
  teaser: /assets/images/cloud-teaser.png

categories:
  - 개발
tags:
  - 
  - AWS
  - GCP
  - Azure
last_modified_at: 2020-10-15T13:50:00-00:00
---
![]({{ site.url }}{{ site.baseurl }}/assets/images/node-js.png   ){: .align-center}


## 1. React.js npm install 오류 

프로젝트를 진행하다가 타 컴퓨터에서 작업을 하기위해 npm install 하던 도중 설치에서 막혀버렸적이 있다.

![]({{ site.url }}{{ site.baseurl }}/assets/images/nodejs-static_library-error.png   ){: .align-center}


> ~~/.node_modules/grpc/node_modules/.bin/node-pre-gyp" "install" "--fallback-to-build" "--library=static_library

이게 뭘까?🤔...  뭔가 정적 라이브러리에서 꼬인거 같은데....    
yarn install 과 npm install 온갖 방법을 써도 해결이 되지 않았던 적이 있었다...     
   

    
    
***
   

## 2. Windows10 / Mac os, Linux 해결 방밥 해결 방법

### 2-1. Windows10 설치 방법

#### [Chocolatey](https://chocolatey.org/install)

**Powershell** 창에서 (CMD X) 
```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))   
```

를 복사 붙여넣기하여 설치를 한다

#### [Meteor](https://www.meteor.com/install)

똑같이 **Powershell** 창에서 
>choco install meteor  

를 복사 붙여넣기하여 설치를 한다


## 2-2. Mac os, Linux(ubuntu, etc...)

#### [Meteor](https://www.meteor.com/install)
**Command**  창에서

```
curl https://install.meteor.com/ | sh
```

설치를 한다

## 3. 공통 커맨드 

다시 작업 창으로 돌아와   

```
meteor npm install --save @babel/runtime
```







-끝-