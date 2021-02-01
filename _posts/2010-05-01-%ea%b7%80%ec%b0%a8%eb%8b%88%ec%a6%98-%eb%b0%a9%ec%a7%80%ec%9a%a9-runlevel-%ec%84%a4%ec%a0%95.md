---
title: '귀차니즘 방지용 &#8211; Runlevel 설정.'
author: netggio
layout: post
permalink: /archives/1768
categories:
  - 일~일~일/Script 모음
tags:
  - chkconfig
  - runlevel
  - script
---
귀차니즘 방지용.

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  <br /> 
  
  <P>
    #!/bin/bash
  </P>
  
  <br /> 
  
  <P>
    Demon=`chkconfig &#8211;list | awk &#8216;{print $1}&#8217; | grep -v &#8216;:&#8217;`
  </P>
  
  <br /> 
  
  <P>
    for disable in $Demon <BR />&nbsp;<BR />&nbsp; do<BR />&nbsp; &nbsp; &nbsp;&nbsp; chkconfig &#8211;level 3 $disable off<BR />done<BR /><BR />chkconfig &#8211;level 3 xinetd on<BR />chkconfig &#8211;level 3 crond on<BR />chkconfig &#8211;level 3 iptables on<BR />chkconfig &#8211;level 3 syslog on<BR />chkconfig &#8211;level 3 network on<BR />chkconfig &#8211;level 3 sshd&nbsp; on
  </P>
</DIV>