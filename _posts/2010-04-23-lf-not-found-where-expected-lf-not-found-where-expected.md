---
title: LF not found where expected LF not found where expected
author: netggio
layout: post
permalink: /archives/1749
categories:
  - 일~일~일/linux
tags:
  - pop3에러
---
  
pop3메일 받을시&#8230; 메일이 안 받아지는 경우 발생 ;  
  
&nbsp;메일섭에서 보니 이런 로그가 ;;  
  
/var/mail/계정명: LF not found where expected LF not found where expected  
  
구굴링 결과 버그라넹.. 이런 경우 발생시 아래의 방법으로 대처  
  
ex> 메일 계정은 alex라고 가정함  
  
&nbsp; &nbsp; &nbsp; &nbsp;사전에 백업은 필수.  
  
&nbsp; &nbsp; &nbsp;&nbsp; ./var/mail/&nbsp; 폴더로 이동. alex 이라는 메일박스 이름을 alex_bk로 복사함  
  
&nbsp; &nbsp; &nbsp;&nbsp; formail -ds <alex_bk >>alex   
  
잘 처리됨.