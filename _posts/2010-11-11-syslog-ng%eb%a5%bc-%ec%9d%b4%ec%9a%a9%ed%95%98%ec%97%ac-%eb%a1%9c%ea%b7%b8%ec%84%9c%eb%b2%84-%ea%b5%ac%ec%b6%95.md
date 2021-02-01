---
title: syslog-ng를 이용하여 로그서버 구축
author: netggio
layout: post
permalink: /archives/1900
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - syslog
  - syslog-ng
  - 로그서버
  - 시스템로그
---
syslog로&nbsp; 원격지의 시스템 로그를 받아 볼수 있지만&#8230;   
  
로그를 보내는 클라이언트 수가 많은 경우 골치 아파진다.   
  
날짜별.. 호스트별&#8230; 구분해서 저장해야 관리가 되는데 syslog로는 역부족 하다.  
  
  
syslog-ng가 &nbsp;이러한 모든 고민을 해결해준다.   
  
시스템 log서버를 별도로 만들려고 하는경우 &nbsp;로그를 받는 로그서버에만   
syslog.-ng를 설치 해주면 된다&nbsp; 편하게 rpm으로~ ㄱㄱㄱ.  
  
  
**&#8211; 클라이언트 서버 설정 &#8211;  
**  
우선&nbsp; 로그를 보내는 클라이언트 서버의&nbsp; /etc/syslog.conf 열어서   
아래의 부분 추가 후 syslog&nbsp; 리스타트

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  *.* &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; @로그서버 IP
</DIV>

  


**  
  
&#8211; 로그 서버 설정 &#8211;  
**  
우선 아래의 syslog-ng 설치 [ rhel4 /centos4&nbsp; 기준]  
<A href="ftp://ftp.pbone.net/mirror/ftp.silfreed.net/repo/rhel/4/x86\_64/silfreednet/RPMS/syslog-ng-1.6.8-1.el4.i386.rpm" target=\_blank>[<INS><FONT color=#0000ff>ftp://ftp.pbone.net/mirror/ftp.silfreed.net/repo/rhel/4/x86_64/silfreednet/RPMS/syslog-ng-1.6.8-1.el4.i386.rpm</FONT></INS>][1]  
</A>  
기존의&nbsp; syslog 지우지 않고 설치 해도 무관하다.  
  
/etc/syslog-ng/syslog-ng.conf 파일 백업 해 두고 아래의 내용으로 변경 한다

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  options { sync (0);<BR />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; time_reopen (10);<BR />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; log_fifo_size (1000);<BR />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; long_hostnames (off);<BR />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; use_dns (no);<BR />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; use_fqdn (no);<BR />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; create_dirs (no);<BR />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; keep_hostname (yes);<BR />&nbsp; &nbsp; &nbsp; &nbsp; };<BR /><BR />source local {<BR />&nbsp; &nbsp; &nbsp; &nbsp; unix-stream(&#8220;/dev/log&#8221;);<BR />&nbsp; &nbsp; &nbsp; &nbsp; internal();<BR />};<br /> 
  
  <P>
    source LOG_ZONE &nbsp;{<BR />&nbsp; &nbsp; &nbsp; &nbsp; udp(ip(0.0.0.0) port(514)); &nbsp;&nbsp; # 포트는 바꾸고 싶은걸로 바꾸도 무관
  </P>
  
  <br /> 
  
  <P>
    };
  </P>
  
  <br /> 
  
  <P>
    destination hosts {<BR />&nbsp; &nbsp; &nbsp; &nbsp; file(&#8220;/home/SYSTEM_LOG/$YEAR/$MONTH/$DAY/$HOST/$FACILITY&#8221;<BR />&nbsp; &nbsp; &nbsp; &nbsp; owner(root) group(root) perm(0600) dir_perm(0700)<BR />create_dirs(yes));<BR />};
  </P>
  
  <br /> 
  
  <P>
    log {<BR />&nbsp; &nbsp; &nbsp; &nbsp; source(local);<BR />&nbsp; &nbsp; &nbsp; &nbsp; destination(hosts);<BR />};
  </P>
  
  <br /> 
  
  <P>
    log {<BR />&nbsp; &nbsp; &nbsp; &nbsp; source(LOG_ZONE);<BR />&nbsp; &nbsp; &nbsp; &nbsp; destination(hosts);<BR />};
  </P>
</DIV>

  


방화벽 udp 514포트 오픈 , syslog-ng 리스타트   
  
이렇게 하면&#8230;   
  
원격지에 있는 서버들의 시스템 로그들이 /home/SYSTEM_LOG/년/월/일/ip/  
  
형식으로 구분되어서 저장되는것을 볼수 있을것이다.

 [1]: ftp://ftp.pbone.net/mirror/ftp.silfreed.net/repo/rhel/4/x86_64/silfreednet/RPMS/syslog-ng-1.6.8-1.el4.i386.rpm