---
title:  "Mac OS Python Nmap 에러 "
excerpt: "Nmap 에러 오류"
toc: true
toc_sticky: true
header:
  teaser: /assets/images/shoes-teaser.jpg

categories:
  - 개발
tags:
  - nmap
  - Python
  - Error
  -  
last_modified_at: 2020-10-15T08:06:00-05:00
---

```
Traceback (most recent call last):
  File "/usr/local/lib/python3.9/site-packages/nmap/nmap.py", line 322, in analyse_nmap_xml_scan
    dom = ET.fromstring(self._nmap_last_output)
  File "/usr/local/Cellar/python@3.9/3.9.0/Frameworks/Python.framework/Versions/3.9/lib/python3.9/xml/etree/ElementTree.py", line 1348, in XML
    return parser.close()
xml.etree.ElementTree.ParseError: no element found: line 1, column 0
```

```
  File "/usr/local/lib/python3.9/site-packages/nmap/nmap.py", line 262, in scan
    return self.analyse_nmap_xml_scan(
  File "/usr/local/lib/python3.9/site-packages/nmap/nmap.py", line 325, in analyse_nmap_xml_scan
    raise PortScannerError(nmap_err)
nmap.nmap.PortScannerError: 'You requested a scan type which requires root privileges.\nQUITTING!\n'
```

## 1. 증상

![]({{ site.url }}{{ site.baseurl }}/assets/images/nmap-error1.jpg   ){: .align-center}
![]({{ site.url }}{{ site.baseurl }}/assets/images/nmap-error2.jpg   ){: .align-center}  
  

위 사진과 같이 에러가 발생하고 nmap이 진행 되지 않을때가 있다.



---
## 2. 원인은 Sudo


ex) 
```
python3 ABC.py 
```
이전에는 위와 같이 실행 했었다. 그렇다 이게 문제였다.   

윈도우에선 분명 문제없이 잘됐는데 MAC OS에선 에러를 뿜어서 한참을 원인을 찾아 다녔는데...   


---
## 3. 해결방법
ex)
```
sudo python3 ABC.py
```

![]({{ site.url }}{{ site.baseurl }}/assets/images/nmap-error3.jpg   ){: .align-center}    
   
nmap 프로그램을 실행 해보고 순간 깨닳았다...

맥북에선 nmap 실행할땐 su권한을 획득하지 않으면 실행이 안된다.    


오류 해결!





