---
title: 'Geoip를 이용한 국가별 iptables 체인 및 차단룰  생성 스크립트'
author: netggio
layout: post
permalink: /archives/1771
categories:
  - 일~일~일/Script 모음
tags:
  - geoip
  - iptables
  - script
  - 국가별차단
---
**  
[ Geoip를 이용한 체인 생성 및 차단룰 생성 스크립트 ]**  
  
Geoip에서 제공 되는 csv파일을 이용하여 국가별 ip리스트를 뽑아 국가별 분류 후  
  
국가 이니셜로 체인룰 생성후 차단룰 파일 생성 스크립트임.  
  
KR도 포함되어 있으니 괜히.. ㅋㅋ.. KR 파일 실행 시키면 ㅋㅋㅋ 대략 난감한 상황 발생 ㅋㅋ  
  
crontab에 5분간격으로 iptables 리스타트 혹은 플래쉬 해주도록 하고 테스트 ㅋㅋ.

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  <br /> 
  
  <P>
    #!/bin/bash<BR /># 2010.05.01&nbsp; by netggio<BR /><BR />Geoip_Tmp=Tmp<BR />Geoip=GeoIPCountryWhois.csv<BR />nation_Dir=NATION_IP<BR />protocol=ALL
  </P>
  
  <br /> 
  
  <P>
    rm -rf &nbsp; $Geoip_Tmp/*<BR />mkdir -p $nation_Dir<BR />mkdir -p $Geoip_Tmp
  </P>
  
  <br /> 
  
  <P>
    wget <A href="http://geolite.maxmind.com/download/geoip/database/GeoIPCountryCSV.zip">http://geolite.maxmind.com/download/geoip/database/GeoIPCountryCSV.zip</A> -P $Geoip_Tmp/
  </P>
  
  <br /> 
  
  <P>
    unzip&nbsp; $Geoip_Tmp/GeoIPCountryCSV.zip&nbsp; -d&nbsp; $Geoip_Tmp/
  </P>
  
  <br /> 
  
  <P>
    for search in `awk -F &#8220;\&#8221;&#8221; &#8216;{ print $10 }&#8217; $Geoip_Tmp/$Geoip&nbsp; | sort | uniq&nbsp; | xargs`
  </P>
  
  <br /> 
  
  <P>
    &nbsp; do<BR />&nbsp; &nbsp;&nbsp; iptables -L -n | grep -w $search > /dev/null
  </P>
  
  <br /> 
  
  <P>
    &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; if [ $? = 1 ];then<BR />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; iptables -N $search<BR />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; iptables -A $search&nbsp; -j RETURN<BR />&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; fi
  </P>
  
  <br /> 
  
  <P>
    &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; grep -w &#8220;$search&#8221; $Geoip_Tmp/$Geoip | awk -F &#8216;\&#8221;&#8216; &#8216;{ print &#8220;iptables -I &#8221; $10&nbsp; &#8221; 1 -p &#8216;$protocol&#8217; -m iprange &#8211;src-range &#8221; <BR />$2 &#8220;-&#8221; $4 &#8221; -j DROP&#8221; }&#8217;&nbsp; > $nation_Dir/$search
  </P>
  
  <br /> 
  
  <P>
    done
  </P>
  
  <br /> 
  
  <P>
    rm -rf &nbsp; $Geoip_Tmp/*
  </P>
  
  <br /> <br />
</DIV>

  


스크립트 실행 하면,&nbsp; Geoip에서&nbsp; 제공되는 국가코드 이름 별로 체인이 생성되고 ,   
  
<IMG style="MARGIN-TOP: 0px; WIDTH: 283px; HEIGHT: 349px" alt="" onerror="if (this.src != '/skin/admin/whitedream/image/spacer.gif') { this.src='/skin/admin/whitedream/image/spacer.gif' }" src="http://blog.netggio.pe.kr/attach/1/1316751249.jpg?randseed=0.10512222978854668" width=75 height=90>  
  
NATION_IP&nbsp; 폴더 밑에 국가 코드명으로 파일이 생성됨 파일 열어보면 차단룰이 들어가게 해났음.<IMG style="MARGIN-TOP: 17px; WIDTH: 469px; HEIGHT: 326px" alt="" onerror="if (this.src != '/skin/admin/whitedream/image/spacer.gif') { this.src='/skin/admin/whitedream/image/spacer.gif' }" src="http://blog.netggio.pe.kr/attach/1/1008676975.jpg?randseed=0.7722666481855219" width=120 height=55>  
  
나머지는 본인 입맛데로 차단을 하던 허용을 하던 ㅋㅋㅋ&#8230; 변경을 하던 본인 숙제 ㅋㅋ  
  
geoip가 갱신 주기에 맞쳐서 주기적으로 &nbsp;업데이트 해주면 될듯.  
  
차단 1순위는 C 모시기 ㅋㅋ&#8230;