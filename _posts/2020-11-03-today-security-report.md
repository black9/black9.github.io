---
title:  "20년 11월 03일 일일 보안 동향 트랜드"
excerpt: "20/11/03 일일 보안 트랜드 및 동향 요약"
toc: true
toc_sticky: true
header:

categories:
  - 보안
tags:
  - Security
last_modified_at: 2020-11-03T05:00:00-08:00
---


## 1. npm 악성 패키지 백도어 이슈
- 라이브러리의 이름은 'twilio-npm' ← 개발자 보안 작업 (DevSecOps) 서비스의 일부   

[트위터](https://twitter.com/ZDNet/status/1323354641510313985)    
[해당 뉴스(영문)](https://www.zdnet.com/article/malicious-npm-package-opens-backdoors-on-programmers-computers/)    
  
  - 현재 짧은 기간임에 불구하고 370 회 이상 다운로드 되었음
  - JavaScript / npm / Node.js 프로젝트 내에서 가져온 모든 컴퓨터에서 **TCP 리버스 쉘**을 열도록 하였음
    - 리버스 쉘은 UNIX 기반 운영 체제에서만 작동  
    

## 2. 북한과 관련된 APT 그룹 Kimsuky가 새로운 악성 코드를 사용하여 발견
- 북한과 관련된 사이버 스파이 그룹 Kimsuky는 최근 정부 기관과 인권 운동가를 대상으로 공격, 새로운 악성 코드를 사용  
  
[트위터](https://twitter.com/modernnetsec/status/1323312971196628994)  
[해당 뉴스(영문)](https://modernnetsec.io/north-korea-linked-apt-group-kimsuky-spotted-using-new-malware/)   
  
- Kimsuky APT 그룹은 여러 보안 팀에 의해 분석 되었으며, 2013 년 Kaspersky 연구원 이 처음 발견
- 북한에 연결된 APT, KGH_SPY라는 모듈 식 스파이웨어 및 CSPY Downloader라는 다운로더와 관련된 두 가지 새로운 멀웨어에 대한 세부 정보가 포함 된 새로운 보고서를 발표
 - 이전에 식별 된 Kimsuky 인프라와 겹치는 사이버 스파이가 사용하는 새로운 서버 인프라를 식별
  ```
    KGH_SPY는 공격자가 정찰, 키 로깅, 정보 도용을 수행하고 백도어 기능을 구현할 수있는 모듈 식 도구 모음
  ```
  ```
    CSPY Downloader는 분석을 회피하도록 설계된 도구이며 추가 페이로드를 제공하는 다운로더 역할
  ```
    
## 3. CVE-2020-17087 Google, Windows 제로 데이 버그 공개
- CfgAdtpFormatPropertyBlock 함수에 있으며 16 비트 정수로 끊어 발생한 문제  

[트위터](https://twitter.com/securetia/status/1323365229460377605)  
[해당 뉴스(영문)](https://thehackernews.com/2020/11/warning-google-discloses-windows-zero.html?m=1#click=https://t.co/tgtxsM9N2u)  
  
- 문제의 커널 드라이버인 Windows 커널 암호화 드라이버 **cng.sys**   
  - CfgAdtpFormatPropertyBlock 함수에 있으며 16 비트 정수로 끊어 문제 발생    
  - Windows 7 이상 버전의 버퍼 오버플로우와 관련  
- \Device\CNG 디바이스를 사용자 모드 프로그램에 노출하고 사소하지 않은 입력 구조로 다양한 IOCTL을 지원  
  - 권한 상승 (예: sandbox escape) 을 위해 악용 될 수있는 로컬 액세스 공격 표면을 구성함
   - 익스플로잇 체인이 CVE-2020-17087을 지난주 Google에서 수정 한 다른 Chrome 브라우저 제로 데이 ( [CVE-2020-15999](https://twitter.com/benhawkes/status/1318640422571266048?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1318640422571266048%7Ctwgr%5Eshare_3&ref_url=https%3A%2F%2Fcybersecuritynews.com%2Fnew-chrome-0-day-bug%2F) ) 과 관련 되어 있음
  [CVE-2020-15999] Chrome 배포판에 포함 된 FreeType 글꼴 렌더링 라이브러리에 존재하는 메모리 손상 취약점
  
  - 문제에 대한 패치는 11월 10 일에 배포 예정

## 4. Wroba 모바일 뱅킹 트로이 목마가 SMS를 통해 확산

[트위터](https://twitter.com/RisingCyberLLC/status/1323377856005738496)
[해당 뉴스(영문)](https://threatpost.com/wroba-mobile-banking-trojan-spreads-us/160785/?utm_content=buffer27177&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer)
 공격흐름 
  1. SMS 내의 메시지에는 링크가 포함되어 있으며 "당신의 소포가 발송되었습니다. 확인하고 수락하십시오” 라는 메세지를 보냄  
  2. Android 사용자를 악성 사이트로 이동하면 브라우저가 최신 버전이 아니므로 업데이트가 필요하다는 경고가 표시(장치에서 사용하는 운영 체제에 따라 다름)  
  3. 사용자가 '확인'을 클릭하면 악성 응용 프로그램이 포함 된 트로이 목마 브라우저 패키지 다운로드  
    - 실행 파일은 iPhone에서 작동하지 않음  
    - 장치가 감염되면 Wroba는 훔친 연락처 목록 및 SMS 기능과 같은 일부 기능을 사용하여 전파하고 감염된 장치를 사용하여 호스트에서 오는 것으로 위장하여 악성 링크가 포함 된 SMS를 전송하여 더 확산  
    

## 5. GitHub CDN의 SSL 만료 이슈

[트위터](https://twitter.com/Gurgling_MrD/status/1323395864212234245)  
[해당 뉴스(영문)](https://www.bleepingcomputer.com/news/security/github-breaks-site-layout-after-forgetting-to-renew-certificate/)   

- 2020.11.02  PM 06:00 (BST)  → 한국시각 2020.11.03 AM 03:00(KST)만료였으나 Github회사 측 SSL 갱신을 안함   
   CDN (콘텐츠 전송 네트워크) : 서로 다른 지리적 위치에 전략적으로 배치 된 기본 웹 사이트의 서버와 분산 된 구성
 ![]({{ site.url }}{{ site.baseurl }}/assets/images/github-cert-error.png){: .align-center}   

- 만료 된 인증서로 인해 이미지, JavaScript 및 CSS 스타일 시트와 같은 수많은 리소스가 GitHub에 올바르게 불러오지 못함  
![]({{ site.url }}{{ site.baseurl }}/assets/images/github-cert-error2.png){: .align-center}  
  - [github 인증서 갱신 등록](http://github.githubassets.com/) 도메인에 새 인증서 설치를 하였으나 2021 년 11 월에 만료예정  
  - 웹 기술과 IoT 장치가 보안 강화와 " 모든 곳에서 HTTPS" 접근 방식 으로 이동함에 따라 고객의 불편을 최소화하기 위해 산업 전반에 걸쳐 워크 플로우와 프로세스를 수정해야 함  
  - SSL 인증서 갱신을 적절한 계획을 통해 완전히 예방할 수 있도록 해야 함.

- 번외) 인증서 만료 문제  
  - 지난주, 전 세계 HP 사용자 프린터 인증서가 취소 된 후 Apple 장치에서 인쇄 할 수 없는 현상 발생  
  [Apple, HP 인증서 폐기해 MacOS에서 프린터 사용 불가](https://blog.alyac.co.kr/3335)
  - 올해 초, Roku TV 채널은 글로벌 인증서 만료 문제로 인해 소비자가 림보에 빠지면서 스트리밍이 중단 현상 발생  
  [Expiring SSL certs expected to break smart TVs, fridges, and IoTs](https://www.bleepingcomputer.com/news/security/expiring-ssl-certs-expected-to-break-smart-tvs-fridges-and-iots/)
