---
title: '[perl] 포트 체크 스크립트'
author: netggio
layout: post
permalink: /archives/1661
categories:
  - 일~일~일/Script 모음
tags:
  - perl
  - script
  - 포트체크
---
일전에 일하다 필요해서 급조로 짠 초간단 펄 스크립트..  
  
응용하면 쓸만한 스크립트일듯.   
  
=====&nbsp; 이하 config.ini &nbsp;파일 =====   
<FONT color=#0000ff>

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  <FONT color=#0000ff>[Dest_Server] <BR />; 체크할 대상의 ip 설정, 대상이 여러개의 호스트일 경우 구분자는 쉼표<BR />Dest_Server_IP=127.0.0.1<BR />[Dest_Server_Port]<BR />; 체크할 대상의 포트 설정<BR />PORT=80<BR />[Check_Time]<BR />; 포트 체크시 타임아웃 설정<BR />TIME=0.5</FONT>
</DIV>

  


</FONT>  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   
  
===== &nbsp; 이하 Check_port.pl&nbsp; 파일=====  
<FONT color=#0000ff>

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  <br /> 
  
  <P>
    <FONT color=#0000ff>#!/usr/bin/perl </FONT>
  </P>
  
  <br /> 
  
  <P>
    <FONT color=#0000ff># by netggio<BR />###&nbsp; </FONT><A href="http://netggio.pe.kr/"><FONT color=#0000ff>http://netggio.pe.kr</FONT></A>
  </P>
  
  <br /> 
  
  <P>
    <FONT color=#0000ff>use strict;<BR />use warnings;<BR />use CGI;<BR />use Net::Ping;<BR />use LWP::Simple;<BR />use Config::IniFiles;<BR />my $ip ;<BR />; config.ini 파일 위치 기입<BR />my $file = &#8220;/usr/local/tools/script/config.ini&#8221;;<BR />my $ini = Config::IniFiles->new(<BR />&nbsp; &nbsp; -file &nbsp;&nbsp; => $file<BR />&nbsp; &nbsp; ) or die &#8220;Could not open $file!&#8221;;</FONT>
  </P>
  
  <br /> 
  
  <P>
    <FONT color=#0000ff>my $Client_config=$ini->val(&#8216;Dest_Server&#8217;,&#8217;Dest_Server_IP&#8217; );<BR />my @Dest_host=split(/,/, $Client_config);</FONT>
  </P>
  
  <br /> 
  
  <P>
    <FONT color=#0000ff>my $Client_port_config=$ini->val(&#8216;Dest_Server_Port&#8217;,&#8217;PORT&#8217; );</FONT>
  </P>
  
  <br /> 
  
  <P>
    <FONT color=#0000ff>my $CHECK=$ini->val(&#8216;Check_Time&#8217;,&#8217;TIME&#8217; );</FONT>
  </P>
  
  <br /> 
  
  <P>
    <BR /><FONT color=#0000ff>foreach my $ip (@Dest_host)</FONT>
  </P>
  
  <br /> 
  
  <P>
    <FONT color=#0000ff>{<BR />&nbsp; &nbsp; &nbsp; &nbsp; my $p = Net::Ping->new(&#8216;tcp&#8217;, $CHECK);<BR />&nbsp; &nbsp; &nbsp; &nbsp; $p->tcp_service_check(1);<BR />&nbsp; &nbsp; &nbsp; &nbsp; my $host = &#8220;$ip&#8221;;<BR />&nbsp; &nbsp; &nbsp; &nbsp; $p->{&#8216;port_num&#8217;} = &#8220;$Client_port_config&#8221;;<BR />&nbsp; &nbsp; &nbsp; &nbsp; print &#8220;$host &#8211;> port $Client_port_config is &#8220;,</FONT>
  </P>
  
  <br /> 
  
  <P>
    <FONT color=#0000ff>&nbsp; &nbsp; &nbsp;&nbsp; ($p->ping($host) ? &#8220;<b><font color=&#8217;blue&#8217;>up</font color></b><br>&#8221; : &#8220;<b><font color=&#8217;red&#8217;>down</font color></b><br>&#8221;);</FONT>
  </P>
  
  <br /> 
  
  <P>
    <FONT color=#0000ff>}<BR /></FONT><BR />
  </P>
</DIV>

  


</FONT>===================================  
  
간단 사용법  
perl Check_port.pl > Result.html  
  
html로 결과 저장됨.