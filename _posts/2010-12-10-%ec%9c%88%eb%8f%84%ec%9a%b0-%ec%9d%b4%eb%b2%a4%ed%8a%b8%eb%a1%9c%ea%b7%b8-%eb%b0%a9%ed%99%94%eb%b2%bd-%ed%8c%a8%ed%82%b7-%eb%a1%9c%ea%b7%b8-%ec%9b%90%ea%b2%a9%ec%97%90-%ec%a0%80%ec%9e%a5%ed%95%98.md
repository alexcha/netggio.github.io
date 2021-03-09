---
title: 윈도우 이벤트로그/ 윈도우 방화벽 패킷 로그 원격에 저장하기
author: netggio
layout: post
permalink: /archives/1905
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - syslog-ng
  - winsyslog
  - 로그서버
  - 패킷로그
---
<FONT face="'Arial','helvetica','sans-serif'">리눅스 같은 경우 syslog를 이용하여 간단하게 리모트에 로그를 남길수 있었는데 문제는 윈도우였다 ;;; <BR /><BR />이넘의 이벤트 로그&#8230; 패킷로그 ㅋㅋㅋ<BR /><BR />다행히도~ freeware로 제공되는 syslog&nbsp; clinet 가 있다~.<BR /><BR /></FONT><A href="http://syslogserver.com/download.html" target=_blank><A href="http://syslogserver.com/download.html" target=_blank><A href="http://syslogserver.com/download.html" target=_blank><FONT face="'Arial','helvetica','sans-serif'">http://syslogserver.com/download.html</FONT></A>  
  
</A></A><FONT face="'Arial','helvetica','sans-serif'"><FONT size=2><STRONG>Datagram SyslogAgent v3.5 (Free software) 다운로드 후 설치<BR /><BR /><IMG style="MARGIN-TOP: 0px; WIDTH: 411px; HEIGHT: 282px" alt="" onerror="if (this.src != '/skin/admin/whitedream/image/spacer.gif') { this.src='/skin/admin/whitedream/image/spacer.gif' }" src="/attach/1/4131726689.gif?randseed=0.5147736407864034" width=107 height=90><BR /><BR /></STRONG></FONT><FONT size=2>추가적으로 어플리케이션 로그가 지원되므로~ 윈도우방화벽 패킷로그도 </FONT></FONT><FONT size=2 face="'Arial','helvetica','sans-serif'">원격에 쌓을수 있다. ㅎㅎㅎ ..   
  
윈도우 경우 패킷로그 쌓는 사이즈 제한이 있어서 로그를 놓친는 경우가 있었는데 이것으로 인해 고민거리 해결 ㅎ.</FONT>

  


<FONT face="'Arial','helvetica','sans-serif'"><FONT size=2>리눅스는 syslog로 윈도는 Syslogagent를 이용하여 130여대 장비 대상으로 테스트로 돌려보고 있다</FONT><FONT size=2>~~.&nbsp; 잘된다~ ㅎ</FONT></FONT>

  


<FONT size=2 face="'Arial','helvetica','sans-serif'">이것으로 로그 찾는다고.. 이장비 저장비 들낙날락 거리는 번거로움 안녕이고~</FONT>

  


<FONT size=2 face="'Arial','helvetica','sans-serif'">로그의 무결성은 어느정도 지킬수 있지 않을까 싶다.  
</FONT>