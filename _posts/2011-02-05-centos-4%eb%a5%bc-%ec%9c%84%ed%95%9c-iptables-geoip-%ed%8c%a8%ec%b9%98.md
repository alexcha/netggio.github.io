---
title: CentOS-4를 위한 iptables geoip 패치
author: netggio
layout: post
permalink: /archives/1915
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - geoip
  - iptables
  - Netfilter
  - p-o-m-ng
  - 국가별 ip차단
  - 패치
---
centos4기준으로 iptables connlimit&nbsp; 패키징 하면서&nbsp; geoip 패치도 같이 만들어 보았다.   
  
패키징 해놓은것으로 <FONT color=#0000ff>libipt_geoip.so</FONT> , <FONT color=#0000ff>ipt_geoip.ko</FONT>을 한큐에 올릴수 있고,   
  
csv로 geoip데이터를 컨버팅 해주는 유틸 설치 까지 끝낼수 있다.   
  
뭐.. 암튼.. iptables&nbsp; geoip패치를 하게 되면 국가별 차단룰 만드는게 간단해져서 컨트롤이&nbsp; 쉬워지는 장점이 있다.   
  
  
**[사전작업]  
**<FONT color=#333333>작업에 앞서 사전작업이 필요하다&#8230;. 사전작업 이래봐야 별거 없다 ㅋㅋ&#8230;  
현재 설치되어 있는 iptables의 src.rpm 구해서 아래와 같이만 해놓으면 &nbsp;된다..</FONT><FONT color=#ff0000>

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  <FONT color=#ff0000>rpm -ivh iptables-1.2.11-3.2.RHEL4.src.rpm<BR />rpmbuild -bp /usr/src/redhat/SPECS/iptables.spec &#8211;target=`uname -r`<BR />ln -s /usr/src/redhat/BUILD/iptables-1.2.11/&nbsp; &nbsp;/usr/src/iptables<BR /></FONT>
</DIV></FONT>

  


이것으로 .사전작업은 끝 ㅋㅋ..  
  
centos4는 디폴트가 1.2.11버전일것이다.   
  
이제~ 패키징해 놓은 압축파일 받아다가 폴더 안에 있는 geo.sh만 실행 해주면 끝난다.  
  
**다운로드 -> **&nbsp;<FONT size=2>**[<FONT size=2>**POM-NG\_geoip\_CentOS-4.tar.gz  
**</FONT>][1]**</FONT><img src="http://netggio.pe.kr/wp-content/uploads/1/1331287506.gif" class="aligncenter" width="450" height="482" alt="사용자 삽입 이미지" />&nbsp;별문제 없었다면 libipt\_geoip.so , ipt\_geoip.ko 올라온거 확인 될거고, csv2bin등..   
geoip_tools이 인스톨되어 있을것이다.  
  
  
이제 국가별ip데이터를 받아다가 iptables가 인식할수 있게 컨버팅만 해주면 된다  
ip데이터는 여기서~ <http://geolite.maxmind.com/download/geoip/database/GeoIPCountryCSV.zip>  
  
컨버팅은 csv2bin을 이용하면 된다. 방법은 아래 스샷 참고.&nbsp; <img src="http://netggio.pe.kr/wp-content/uploads/1/6762662780.gif" class="aligncenter" width="450" height="213" alt="사용자 삽입 이미지" />그리고 국가별룰이 올라오는지 확인~   
  
간단 사용법은 iptables -m geoip &#8211;help으로 알아 볼 수 있다.  
  
&nbsp;ip데이터는 주기적으로 변동되므로 각자 알아서 스케줄을 돌려, 갱신해주면 되겠다.  
  
커널 업데이트등 현재 사용하는 커널을 변경하게되면 &nbsp;인스톨 스크립트를 다시 돌려줘야 커널에 맞게끔 모듈이 올라온다.  
  
  
귀차니즘 안녕~~  
  
관련 사이트   
http://people.netfilter.org/peejix/geoip/howto/geoip-HOWTO.html#toc1   
</A>http://geolite.maxmind.com

 [1]: http://blog.netggio.pe.kr/d_file/POM-NG_geoip_CentOS-4.tar.gz