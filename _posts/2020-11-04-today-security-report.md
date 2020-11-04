---
title:  "20년 11월 4일 일일 보안 동향 트랜드 및 뉴스"
excerpt: "20/11/04 일일 보안 트랜드 및 동향 요약"
toc: true
toc_sticky: true
header:

categories:
  - 보안
tags:
  - Security
last_modified_at: 2020-11-04T05:00:00-08:00
---

# [11/04]일일 보안 동향 보고 요약
   
## 1. 북한 해커 그룹 'Kimsuky' 강화된 스파이웨어 모듈

[트위터](https://twitter.com/risingcyberllc/status/1323666259544809474)  
[해당 뉴스(영문)](https://thehackernews.com/2020/11/new-kimsuky-module-makes-north-korean.html?utm_content=buffer796cd&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer)  

![]({{ site.url }}{{ site.baseurl }}/assets/images/north-kor-attack-main.jpg ){: .align-center}  
  
- Kimsuky는 감염 시작으로는 감염 된 Word 문서에 코로나 바이러스 테마로 피해자 이메일로 보내어 실행시킨 컴퓨터에  멀웨어 공격 시작  
![]({{ site.url }}{{ site.baseurl }}/assets/images/north-kor-attack.png ){: .align-center}  
- 역할   
	- KGH_SPY 백도어는 명령 및 제어 (C2) 서버에서 보조 페이로드를 다운로드하고 cmd.exe 또는 PowerShell을 통해 임의의 명령을 실행하며 웹 브라우저, Windows Credential Manager, WINSCP 및 메일 클라이언트에서 자격 증명을 수집    
	- "KGH_SPY"라는 모듈 식 스파이웨어 제품군을 통해 새로운 기능을 획득하여 대상 네트워크를 정찰하고 키 입력을 캡처하며 민감한 정보를 훔침  

## 2. 중요 웹 로직 서버의 결함에 대한 오라클 rushes 긴급 수정
[트위터](https://twitter.com/whitehead4jeff/status/1323722247631216640)  
[해당 뉴스(영문)](https://threatpost.com/oracle-update-weblogic-server-flaw/160889/)   
  
![]({{ site.url }}{{ site.baseurl }}/assets/images/oracle.jpg ){: .align-center}  
  
- Oracle WebLogic Server는 엔터프라이즈 Java EE 애플리케이션을 구축하고 배포하는 데 사용되는 널리 사용되는 애플리케이션 서버   
- 최근 취약점 ( [CVE-2020-14750](https://www.oracle.com/security-alerts/alert-cve-2020-14750.html#AppendixFMW)) 은 CVSS 기본 점수 10 점 만점에 9.8 점을 받음   
- 인증없이 원격으로 악용 할 수 있음 (ID와 PW없이 네트워크를 통해 악용 됨)   
- 약점의 심각성에, 오라클은 고객이, 10 월 (2020) 크리티컬 패치 업데이트를 적용한 후 가능한 한 빨리 보안 경고에서 제공하는 업데이트를 적용하는 것이 좋음  

- Oracle WebLogic 서버는 지금까지 계속 공격을 받고 있음  
    - 2019 년 5 월 연구원들은 REvil / Sodinokibi 랜섬웨어 확산을 포함하여 최근에 공개 된 Oracle WebLogic 중요 역직렬화 취약점 (CVE-2019-2725)을 악용하는 악성 활동 이 급증하고 있다고 경고   
    - 2019 년 6 월 Oracle은 WebLogic Server ( CVE-2019-2729 ) 의 중요한 원격 코드 실행 결함이 적극적으로 악용되고 있다고 말함.   

## 3. Chrome 브라우저 익스플로잇이 공격하는 취약점 차단 패치
  
[트위터](https://twitter.com/securitynewsbot/status/1323731721829842944)   
[해당 뉴스(영문)](https://threatpost.com/chrome-holes-actively-targeted/160890/)   
   
![]({{ site.url }}{{ site.baseurl }}/assets/images/Google-Chrome-Browser.jpg ){: .align-center}  
   
- Chrome 데스크톱 및 Android 브라우저 모두에 대한 패치는 알려진 악용을 통해 심각도가 높은 결함을 해결   
- Chrome은 적극적으로 악용되고 있던 두 가지 추가 취약점을 수정   
    - CVE-2020-16009는 원격 코드 실행에 사용되는 v8 버그   
    - CVE-2020-16010은 Android 용 Chrome SandBox escape   
	

## 4. SaltStack, 신규 취약점 공개 패치
   
[트위터](https://twitter.com/Gurgling_MrD/status/1323720482261213187)   
[해당 뉴스(영문)](https://www.bleepingcomputer.com/news/security/saltstack-reveals-new-critical-vulnerabilities-patch-now/)   
   
![]({{ site.url }}{{ site.baseurl }}/assets/images/saltstack.jpg ){: .align-center}  
   
- CVE-2020-16846 (높음 / 중요)   
    - SaltStack SSH 클라이언트에서 "subprocess.call"을 호출 할 때shell = tru 옵션을 제거하여 패치 된 셸 주입 취약점   
    - 서브 프로세스 파이썬 모듈은 시스템에 당신 산란 새로운 프로세스를 할 수 있습니다.   
    - 외부 사용자 입력 으로 구성된 명령 과 shell = true 옵션을 사용 하여 옵션을 호출하는 것은 알려진 보안 위험   
- CVE-2020-25592은 (높음 / 긴급)   
    - Salt API를 실행하는 사용자에게 영향   
    - Salt-netapi는 eauth 자격 증명 및 토큰을 부적절하게 검증   
- CVE-2020-17490 (낮음)  
    - 암호화 개인 키 파일을 열거 나 저장할 때 액세스 모드가 아닌 권한 문제와 관련   
    - create_ca, create_csr 및 create_self_signed_cert 함수를 사용한 모든 미니언 또는 마스터에 영향   
   
- [링크](https://gitlab.com/saltstack/open/salt-patches) 에서 보안 패치를 다운로드 할 수 있음
   
## 5.WhatsApp 특정 버전 메모리 손상, 충돌 등 이벤트 발생
   
[트위터](https://twitter.com/VulmonFeeds/status/1323742582934016009)   
[CVE-2020-1909](https://vulmon.com/vulnerabilitydetails?qid=CVE-2020-1909)   
    
![]({{ site.url }}{{ site.baseurl }}/assets/images/whatsapp.png){: .align-center}  
    
- WhatsApp v2.20.111 이전의 iOS 용 WhatsApp Business의 로깅 라이브러리에서 사용 후 메모리 손상, 충돌 및 잠재적으로 코드 실행이 발생   
    - WhatsApp 화상 통화를 보류하는 동안 애니메이션 스티커를 받은 것을 포함하여 여러 이벤트가 순서대로 함께 발생한 경우에만 발생   
