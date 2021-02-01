---
title: 윈도우용 포트스캔툴 PortQry
author: netggio
layout: post
permalink: /archives/1897
categories:
  - 일~일~일/windows
tags:
  - PortQry
  - 윈도우용 포트스캔툴
---
윈도우용 포트 스캔 툴이다. 별다른 설치과정이 필요 없고 받아다가 system32폴더에 저장.. dos에서 사용하면 된다.  
  
<A href="http://www.microsoft.com/downloads/en/details.aspx?familyid=89811747-C74B-4638-A2D5-AC828BDC6983&displaylang=en" target=_blank><A href="http://www.microsoft.com/downloads/en/details.aspx?familyid=89811747-C74B-4638-A2D5-AC828BDC6983&displaylang=en" target=_blank><FONT color=#009966 size=2>**http://www.microsoft.com/downloads/en/details.aspx?familyid=89811747-C74B-4638-A2D5-AC828BDC6983&displaylang=en**</FONT></A>  
</A></A></A></A>  
기본 사용법  
&nbsp; portqry -n 대상호스트 -e 포트 -p tcp  
&nbsp; portqry -n 대상호스트 -e 포트 -p udp  
&nbsp; portqry -n 대상호스트 -e 포트 -p both

  


다수의 포트 스캔  
&nbsp;portqry -n 대상호스트 -p tcp -o 53,21.80

  


특정 범위 스캔  
&nbsp; portqry -n 대상호스트 -p tcp -r 51:55

  


&nbsp;-l 옵션을 추가해서 로그 남길수 있음  
  
  
추가 사용방법  
  
&nbsp;<A href="http://support.microsoft.com/kb/832919/ko" target=_blank><A href="http://support.microsoft.com/kb/832919/ko" target=_blank>**<FONT color=#009966 size=2><INS>http://support.microsoft.com/kb/832919/ko</INS></FONT>**</A>  
</A>