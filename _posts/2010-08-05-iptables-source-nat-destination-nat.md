---
title: Iptables Source NAT / Destination NAT
author: netggio
layout: post
permalink: /archives/1824
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - dnat
  - iptables
  - nat
  - snat
---
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal>**<SPAN style="COLOR: #1f497d" lang=EN-US><?xml:namespace prefix = o ns = "urn:schemas-microsoft-com:office:office" /><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN>**

**<SPAN style="FONT-SIZE: 13pt" lang=EN-US><FONT color=#000000><FONT face="맑은 고딕">Iptables Source NAT / Destination NAT<o:p></o:p></FONT></FONT></SPAN>**

  
<P style="TEXT-ALIGN: center; MARGIN: 0cm 0cm 0pt" class=MsoNormal align=center>**<SPAN style="FONT-SIZE: 13pt" lang=EN-US><o:p><FONT color=#000000 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN>**</P>  
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN lang=EN-US><o:p><FONT color=#000000 size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>eth1</SPAN>이 외부와 연결 되어 있고 사설<SPAN lang=EN-US> ip 192.168.100.10</SPAN>를 공인<SPAN lang=EN-US> ip 122.12.12.12</SPAN>로<SPAN lang=EN-US>SNAT/ DNAT</SPAN></FONT></FONT></FONT></P>  
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕">하는 예제 이다<SPAN lang=EN-US>. </SPAN>노란색으로 된 부분만 유동적으로 처리 하면된다<SPAN lang=EN-US>.</SPAN></FONT></FONT></FONT></P>  
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal>**<SPAN lang=EN-US><o:p><FONT color=#000000 size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN>**</P>  
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal>**<FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>1, SNAT/ DNAT </SPAN>추가<SPAN lang=EN-US><o:p></o:p></SPAN></FONT></FONT></FONT>**</P>  
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN lang=EN-US><o:p><FONT color=#000000 size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>1-1, </SPAN>가상 이더넷 추가 </FONT></FONT></FONT></P>  


  
<TABLE style="MARGIN: auto auto auto 10pt; BORDER-COLLAPSE: collapse; BACKGROUND: black; mso-yfti-tbllook: 1184; mso-padding-alt: 0cm 0cm 0cm 0cm" class=MsoNormalTable border=0 cellSpacing=0 cellPadding=0>  
  


<TR style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes">
  <br /> <TD style="BORDER-BOTTOM: black 1pt solid; BORDER-LEFT: black 1pt solid; PADDING-BOTTOM: 0cm; BACKGROUND-COLOR: transparent; PADDING-LEFT: 5.4pt; WIDTH: 441.95pt; PADDING-RIGHT: 5.4pt; BORDER-TOP: black 1pt solid; BORDER-RIGHT: black 1pt solid; PADDING-TOP: 0cm" vAlign=top width=589><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT size=2><FONT face="맑은 고딕"><SPAN style="COLOR: white" lang=EN-US>ifconfig </SPAN><STRONG><SPAN style="COLOR: yellow" lang=EN-US>eth1:3</SPAN></STRONG><SPAN style="COLOR: yellow" lang=EN-US> <STRONG>12.1.12.12</STRONG></SPAN><SPAN style="COLOR: white" lang=EN-US> netmask </SPAN><B style="mso-bidi-font-weight: normal"><SPAN style="COLOR: yellow" lang=EN-US>255.255.255.0</SPAN></B><SPAN style="COLOR: white" lang=EN-US> up<o:p></o:p></SPAN></FONT></FONT></P></TD>
</TR></TABLE>

  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>1-2,</SPAN>가상 이더넷 정보 저장</FONT></FONT></FONT></P>  


  
<TABLE style="MARGIN: auto auto auto 10pt; BORDER-COLLAPSE: collapse; BACKGROUND: black; mso-yfti-tbllook: 1184; mso-padding-alt: 0cm 0cm 0cm 0cm" class=MsoNormalTable border=0 cellSpacing=0 cellPadding=0>  
  


<TR style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes">
  <br /> <TD style="BORDER-BOTTOM: black 1pt solid; BORDER-LEFT: black 1pt solid; PADDING-BOTTOM: 0cm; BACKGROUND-COLOR: transparent; PADDING-LEFT: 5.4pt; WIDTH: 441.95pt; PADDING-RIGHT: 5.4pt; BORDER-TOP: black 1pt solid; BORDER-RIGHT: black 1pt solid; PADDING-TOP: 0cm" vAlign=top width=589><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT size=2><FONT face="맑은 고딕"><SPAN style="COLOR: white" lang=EN-US>echo &#8220;DEVICE=</SPAN><SPAN style="COLOR: yellow" lang=EN-US>eth1:3</SPAN><SPAN style="COLOR: white" lang=EN-US> <o:p></o:p></SPAN></FONT></FONT></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white" lang=EN-US><FONT size=2><FONT face="맑은 고딕">BOOTPROTO=static<o:p></o:p></FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT size=2><FONT face="맑은 고딕"><SPAN style="COLOR: white" lang=EN-US>IPADDR=</SPAN><STRONG><SPAN style="COLOR: yellow" lang=EN-US>12.1.12.12</SPAN></STRONG><SPAN style="COLOR: white" lang=EN-US><o:p></o:p></SPAN></FONT></FONT></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT size=2><FONT face="맑은 고딕"><SPAN style="COLOR: white" lang=EN-US>NETMASK=</SPAN><B style="mso-bidi-font-weight: normal"><SPAN style="COLOR: yellow" lang=EN-US>255.255.255.0</SPAN></B><SPAN style="COLOR: white" lang=EN-US><o:p></o:p></SPAN></FONT></FONT></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white" lang=EN-US><FONT size=2><FONT face="맑은 고딕">ONBOOT=yes<o:p></o:p></FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT size=2><FONT face="맑은 고딕"><SPAN style="COLOR: white" lang=EN-US>TYPE=Ethernet&#8221;>/etc/sysconfig/network-scripts/</SPAN><STRONG><SPAN style="COLOR: yellow" lang=EN-US>ifcfg-eth1:3</SPAN></STRONG><SPAN style="COLOR: #1f497d" lang=EN-US><o:p></o:p></SPAN></FONT></FONT></P></TD>
</TR></TABLE>

  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>1-3,NAT</SPAN>룰 추가</FONT></FONT></FONT></P>  


  
<TABLE style="MARGIN: auto auto auto 10pt; BORDER-COLLAPSE: collapse; BACKGROUND: black; mso-yfti-tbllook: 1184; mso-padding-alt: 0cm 0cm 0cm 0cm" class=MsoNormalTable border=0 cellSpacing=0 cellPadding=0>  
  


<TR style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes">
  <br /> <TD style="BORDER-BOTTOM: black 1pt solid; BORDER-LEFT: black 1pt solid; PADDING-BOTTOM: 0cm; BACKGROUND-COLOR: transparent; PADDING-LEFT: 5.4pt; WIDTH: 441.95pt; PADDING-RIGHT: 5.4pt; BORDER-TOP: black 1pt solid; BORDER-RIGHT: black 1pt solid; PADDING-TOP: 0cm" vAlign=top width=589><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT size=2><FONT face="맑은 고딕"><SPAN style="COLOR: yellow" lang=EN-US><SPAN style="COLOR: white" lang=EN-US>iptables -t nat -A PREROUTING -d <STRONG><SPAN style="COLOR: yellow" lang=EN-US>12.1.12.12</SPAN></STRONG> -j DNAT &#8211;to-destination <SPAN style="COLOR: yellow" lang=EN-US><STRONG>192.168.100.10</STRONG></SPAN><SPAN style="COLOR: yellow" lang=EN-US> </SPAN></SPAN></SPAN></FONT></FONT><FONT size=2><FONT face="맑은 고딕"><SPAN><STRONG><BR /></STRONG><SPAN style="COLOR: white" lang=EN-US><FONT color=#ffffff>iptables -t nat </FONT></SPAN><STRONG><FONT color=#ffffff>-A POSTROUTING -s</FONT> <SPAN style="COLOR: yellow" lang=EN-US>192.168.100.10<FONT style="BACKGROUND-COLOR: #000000"> </FONT></SPAN><FONT color=#ffffff>-j SNAT &#8211;to-source</FONT> <SPAN style="COLOR: yellow" lang=EN-US>12.1.12.12</SPAN></STRONG></SPAN><SPAN style="COLOR: white" lang=EN-US><o:p></o:p></SPAN></FONT></FONT></P></TD>
</TR></TABLE>

  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>1-4,</SPAN>설정 저장 </FONT></FONT></FONT></P>  


  
<TABLE style="MARGIN: auto auto auto 10pt; BORDER-COLLAPSE: collapse; BACKGROUND: black; mso-yfti-tbllook: 1184; mso-padding-alt: 0cm 0cm 0cm 0cm" class=MsoNormalTable border=0 cellSpacing=0 cellPadding=0>  
  


<TR style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes">
  <br /> <TD style="BORDER-BOTTOM: black 1pt solid; BORDER-LEFT: black 1pt solid; PADDING-BOTTOM: 0cm; BACKGROUND-COLOR: transparent; PADDING-LEFT: 5.4pt; WIDTH: 441.95pt; PADDING-RIGHT: 5.4pt; BORDER-TOP: black 1pt solid; BORDER-RIGHT: black 1pt solid; PADDING-TOP: 0cm" vAlign=top width=589><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white" lang=EN-US><FONT size=2><FONT face="맑은 고딕">/etc/init.d/iptables save<o:p></o:p></FONT></FONT></SPAN></P></TD>
</TR></TABLE>

  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>1-5, </SPAN>확인</FONT></FONT></FONT></P>  


  
<TABLE style="BORDER-BOTTOM: medium none; BORDER-LEFT: medium none; MARGIN: auto auto auto 10pt; BORDER-COLLAPSE: collapse; BACKGROUND: black; BORDER-TOP: medium none; BORDER-RIGHT: medium none; mso-yfti-tbllook: 1184; mso-padding-alt: 0cm 5.4pt 0cm 5.4pt; mso-shading: windowtext; mso-pattern: solid auto; mso-border-alt: solid black .5pt; mso-border-themecolor: text1" class=MsoTableGrid border=1 cellSpacing=0 cellPadding=0>  
  


<TR style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes">
  <br /> <TD style="BORDER-BOTTOM: black 1pt solid; BORDER-LEFT: black 1pt solid; PADDING-BOTTOM: 0cm; BACKGROUND-COLOR: transparent; PADDING-LEFT: 5.4pt; WIDTH: 441.95pt; PADDING-RIGHT: 5.4pt; BORDER-TOP: black 1pt solid; BORDER-RIGHT: black 1pt solid; PADDING-TOP: 0cm; mso-border-alt: solid black .5pt; mso-border-themecolor: text1" vAlign=top width=589><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><FONT size=2><FONT color=#ffffff face="맑은 고딕">iptables -L -t nat -n<BR />Chain PREROUTING (policy ACCEPT)<BR />target &nbsp; &nbsp; prot opt source &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; destination &nbsp; &nbsp; &nbsp; &nbsp; <BR />DNAT &nbsp; &nbsp; &nbsp; all&nbsp; &#8212;&nbsp; 0.0.0.0/0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; 12.1.12.12 &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; to:192.168.100.10 </FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><FONT size=2><FONT color=#ffffff face="맑은 고딕">Chain POSTROUTING (policy ACCEPT)<BR />target &nbsp; &nbsp; prot opt source &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; destination &nbsp; &nbsp; &nbsp; &nbsp; <BR />SNAT &nbsp; &nbsp; &nbsp; all&nbsp; &#8212;&nbsp; 192.168.100.10 &nbsp; &nbsp; &nbsp; 0.0.0.0/0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; to:12.1.12.12 </FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><FONT size=2><FONT color=#000000 face="맑은 고딕"><FONT color=#ffffff>Chain OUTPUT (policy ACCEPT)<BR />target &nbsp; &nbsp; prot opt source &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; destination &nbsp; &nbsp; &nbsp; &nbsp; <BR />[root@netggio ~]#</FONT> </FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN lang=EN-US><FONT color=#000000 size=2 face="맑은 고딕">target<SPAN style="mso-spacerun: yes">&nbsp; &nbsp;&nbsp; </SPAN>prot opt source<SPAN style="mso-spacerun: yes">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; </SPAN>destination</FONT></SPAN></P></TD>
</TR></TABLE>

  
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal>**<FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>2, SNAT/ DNAT </SPAN>제거<SPAN lang=EN-US><o:p></o:p></SPAN></FONT></FONT></FONT>**</P>  
<P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>2-1, NAT </SPAN>룰 삭제</FONT></FONT></FONT></P>  


<FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US><br /> <TABLE style="MARGIN: auto auto auto 10pt; BORDER-COLLAPSE: collapse; BACKGROUND: black; mso-yfti-tbllook: 1184; mso-padding-alt: 0cm 0cm 0cm 0cm" class=MsoNormalTable border=0 cellSpacing=0 cellPadding=0><br /> <br /> 

<TR style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes">
  <br /> <TD style="BORDER-BOTTOM: black 1pt solid; BORDER-LEFT: black 1pt solid; PADDING-BOTTOM: 0cm; BACKGROUND-COLOR: transparent; PADDING-LEFT: 5.4pt; WIDTH: 441.95pt; PADDING-RIGHT: 5.4pt; BORDER-TOP: black 1pt solid; BORDER-RIGHT: black 1pt solid; PADDING-TOP: 0cm" vAlign=top width=589><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT size=2><FONT face="맑은 고딕"><SPAN style="COLOR: yellow" lang=EN-US><SPAN style="COLOR: white" lang=EN-US>iptables -t nat -D PREROUTING -d <STRONG><SPAN style="COLOR: yellow" lang=EN-US>12.1.12.12</SPAN></STRONG> -j DNAT &#8211;to-destination <SPAN style="COLOR: yellow" lang=EN-US><STRONG>192.168.100.10</STRONG></SPAN><SPAN style="COLOR: yellow" lang=EN-US> </SPAN></SPAN></SPAN></FONT></FONT><FONT size=2><FONT face="맑은 고딕"><SPAN><STRONG><BR /></STRONG><SPAN style="COLOR: white" lang=EN-US><FONT color=#ffffff>iptables -t nat </FONT></SPAN><STRONG><FONT color=#ffffff>-D POSTROUTING -s</FONT> <SPAN style="COLOR: yellow" lang=EN-US>192.168.100.10<FONT style="BACKGROUND-COLOR: #000000"> </FONT></SPAN><FONT color=#ffffff>-j SNAT &#8211;to-source</FONT> <SPAN style="COLOR: yellow" lang=EN-US>12.1.12.12</SPAN></STRONG></SPAN><SPAN style="COLOR: white" lang=EN-US><o:p></o:p></SPAN></FONT></FONT></P></TD>
</TR></TABLE></P>

<br /> <P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN>  
&nbsp;2-2, </SPAN>설정 저장</FONT></FONT></FONT>

  


  
<TABLE style="MARGIN: auto auto auto 10pt; BORDER-COLLAPSE: collapse; BACKGROUND: black; mso-yfti-tbllook: 1184; mso-padding-alt: 0cm 0cm 0cm 0cm" class=MsoNormalTable border=0 cellSpacing=0 cellPadding=0>  
  


<TR style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes">
  <br /> <TD style="BORDER-BOTTOM: black 1pt solid; BORDER-LEFT: black 1pt solid; PADDING-BOTTOM: 0cm; BACKGROUND-COLOR: transparent; PADDING-LEFT: 5.4pt; WIDTH: 441.95pt; PADDING-RIGHT: 5.4pt; BORDER-TOP: black 1pt solid; BORDER-RIGHT: black 1pt solid; PADDING-TOP: 0cm" vAlign=top width=589><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white" lang=EN-US><FONT size=2><FONT face="맑은 고딕">/etc/init.d/iptables save<o:p></o:p></FONT></FONT></SPAN></P></TD>
</TR></TABLE>

  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>2-3, </SPAN>가상 이더넷 다운</FONT></FONT></FONT></P>  


  
<TABLE style="MARGIN: auto auto auto 10pt; BORDER-COLLAPSE: collapse; BACKGROUND: black; mso-yfti-tbllook: 1184; mso-padding-alt: 0cm 0cm 0cm 0cm" class=MsoNormalTable border=0 cellSpacing=0 cellPadding=0>  
  


<TR style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes">
  <br /> <TD style="BORDER-BOTTOM: black 1pt solid; BORDER-LEFT: black 1pt solid; PADDING-BOTTOM: 0cm; BACKGROUND-COLOR: transparent; PADDING-LEFT: 5.4pt; WIDTH: 441.95pt; PADDING-RIGHT: 5.4pt; BORDER-TOP: black 1pt solid; BORDER-RIGHT: black 1pt solid; PADDING-TOP: 0cm" vAlign=top width=589><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT size=2><FONT face="맑은 고딕"><SPAN style="COLOR: white" lang=EN-US>ifconfig </SPAN><STRONG><SPAN style="COLOR: yellow" lang=EN-US>eth1:3</SPAN></STRONG><SPAN style="COLOR: white" lang=EN-US> down<o:p></o:p></SPAN></FONT></FONT></P></TD>
</TR></TABLE>

  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>2-4</SPAN>가상 이더넷 정보 삭제</FONT></FONT></FONT></P>  


  
<TABLE style="MARGIN: auto auto auto 10pt; BORDER-COLLAPSE: collapse; BACKGROUND: black; mso-yfti-tbllook: 1184; mso-padding-alt: 0cm 0cm 0cm 0cm" class=MsoNormalTable border=0 cellSpacing=0 cellPadding=0>  
  


<TR style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes">
  <br /> <TD style="BORDER-BOTTOM: black 1pt solid; BORDER-LEFT: black 1pt solid; PADDING-BOTTOM: 0cm; BACKGROUND-COLOR: transparent; PADDING-LEFT: 5.4pt; WIDTH: 441.95pt; PADDING-RIGHT: 5.4pt; BORDER-TOP: black 1pt solid; BORDER-RIGHT: black 1pt solid; PADDING-TOP: 0cm" vAlign=top width=589><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><FONT size=2><FONT face="맑은 고딕"><SPAN style="COLOR: white" lang=EN-US>rm -rf /etc/sysconfig/network-scripts/</SPAN><STRONG><SPAN style="COLOR: yellow" lang=EN-US>ifcfg-eth1:3</SPAN></STRONG><SPAN style="COLOR: white" lang=EN-US><o:p></o:p></SPAN></FONT></FONT></P></TD>
</TR></TABLE>

  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><SPAN style="COLOR: #1f497d" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P>  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><FONT color=#000000><FONT size=2><FONT face="맑은 고딕"><SPAN lang=EN-US>2-5, </SPAN>확인</FONT></FONT></FONT></P>  


  
<TABLE style="BORDER-BOTTOM: medium none; BORDER-LEFT: medium none; MARGIN: auto auto auto 10pt; BORDER-COLLAPSE: collapse; BACKGROUND: black; BORDER-TOP: medium none; BORDER-RIGHT: medium none; mso-yfti-tbllook: 1184; mso-padding-alt: 0cm 5.4pt 0cm 5.4pt; mso-shading: windowtext; mso-pattern: solid auto; mso-border-alt: solid black .5pt; mso-border-themecolor: text1" class=MsoTableGrid border=1 cellSpacing=0 cellPadding=0>  
  


<TR style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes">
  <br /> <TD style="BORDER-BOTTOM: black 1pt solid; BORDER-LEFT: black 1pt solid; PADDING-BOTTOM: 0cm; BACKGROUND-COLOR: transparent; PADDING-LEFT: 5.4pt; WIDTH: 441.95pt; PADDING-RIGHT: 5.4pt; BORDER-TOP: black 1pt solid; BORDER-RIGHT: black 1pt solid; PADDING-TOP: 0cm; mso-border-alt: solid black .5pt; mso-border-themecolor: text1" vAlign=top width=589><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><FONT size=2><FONT face="맑은 고딕">iptables -L -t nat -n<o:p></o:p></FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><FONT size=2><FONT face="맑은 고딕">Chain PREROUTING (policy ACCEPT)<o:p></o:p></FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><FONT size=2><FONT face="맑은 고딕">target<SPAN style="mso-spacerun: yes">&nbsp; &nbsp;&nbsp; </SPAN>prot opt source<SPAN style="mso-spacerun: yes">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; </SPAN>destination<SPAN style="mso-spacerun: yes">&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; </SPAN><o:p></o:p></FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><FONT size=2><FONT face="맑은 고딕">Chain POSTROUTING (policy ACCEPT)<o:p></o:p></FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><FONT size=2><FONT face="맑은 고딕">target<SPAN style="mso-spacerun: yes">&nbsp; &nbsp;&nbsp; </SPAN>prot opt source<SPAN style="mso-spacerun: yes">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; </SPAN>destination<SPAN style="mso-spacerun: yes">&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; </SPAN><o:p></o:p></FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><o:p><FONT size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><FONT size=2><FONT face="맑은 고딕">Chain OUTPUT (policy ACCEPT)<o:p></o:p></FONT></FONT></SPAN></P><br /> <P style="MARGIN: 0cm 0cm 0pt" class=MsoNormal><SPAN style="COLOR: white; mso-themecolor: background1" lang=EN-US><FONT size=2 face="맑은 고딕">target<SPAN style="mso-spacerun: yes">&nbsp; &nbsp;&nbsp; </SPAN>prot opt source<SPAN style="mso-spacerun: yes">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; </SPAN>destination</FONT></SPAN></P></TD>
</TR></TABLE>

  
<P style="MARGIN: 0cm 0cm 0pt 10pt; mso-para-margin-left: 1.0gd" class=MsoNormal><SPAN lang=EN-US><o:p><FONT color=#000000 size=2 face="맑은 고딕">&nbsp;</FONT></o:p></SPAN></P></p>