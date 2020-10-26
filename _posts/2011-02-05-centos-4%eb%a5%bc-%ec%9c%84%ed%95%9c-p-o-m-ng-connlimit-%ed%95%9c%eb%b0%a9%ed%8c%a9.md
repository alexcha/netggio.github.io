---
title: 'CentOS-4를 위한 p-o-m-ng connlimit  한방팩~.'
author: netggio
layout: post
permalink: /archives/1913
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - connlimit
  - iptables
  - ipt_connlimit.ko
  - p-o-m-ng
  - 패치
---
<img src="http://netggio.pe.kr/wp-content/uploads/1/3821586356.gif" class="aligncenter" width="450" height="439" alt="사용자 삽입 이미지" />  
iptables connlimit&nbsp; 패치 ㅋㅋ 이것이.. &nbsp;여간 귀찮은게 아니네 ㅡ.ㅡ;&#8217;   
  
기억이 니은이 되어 버리기전에&#8230; 한방에 끝낼수 있게 &nbsp;패키징 했다.. ㅋㅋ   
  
**<FONT color=#000000>&nbsp; &nbsp; 다운로드 -> </FONT>**&nbsp;<A href="http://blog.netggio.pe.kr/d\_file/POM-NG\_connlimit\_CentOS-4.tar.gz" target=\_blank>**<FONT color=#008000 size=2>POM-NG\_connlimit\_CentOS-4.tar.gz  
</FONT>**</A>  
첨부파일 받아다가&nbsp; 풀고,&nbsp; 폴더안에 connlimit.sh 실행~ ㄱㄱㄱ ~ 설치완료~.  
  
단, 운영중인 커널버전의<FONT color=#ff0000>&nbsp;kernel-devel</FONT>과<FONT color=#ff0000> kernel-utils</FONT>은 설치 되어 있어야 된다.  
  
다른 커널로 부팅하게 되는경우.. &nbsp;같은 방법으로 첨부된 폴더 안에 스크립트 실행해주면 모듈생성서 부터 알아서 올려 줄것임.  
  
커널은 건들지 않고 모듈만 올리므로, 시간절약을 할수 있다..  
  
centos4 계열에서는 문제 없이 패치될거 같다.  
  
connlimit 사용법은 각자 알아서~ ㅋㅋㅋ