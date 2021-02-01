---
title: 'error reading information on service xxxxxxx: No such file or directory'
author: netggio
layout: post
permalink: /archives/1816
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - noscripts
  - 브레이드서버
---
<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  sh-3.00# rpm -e xxxxxxxxxx <BR />&nbsp;&nbsp; error reading information on service xxxxxxxxxxx: No such file or directory<BR />&nbsp;&nbsp; error: %preun(xxxxxxxxxxxx) scriptlet failed, exit status 1<BR />sh-3.00#
</DIV>

  


헐.. rpm 안지워져 ;;;.  
  
&nbsp;noscripts 옵션으로&nbsp; 급처리 ;

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  rpm -e&nbsp; xxxxxxxx <FONT color=#d41a01>&#8211;noscripts</FONT>
</DIV>

  


제길&#8230; &nbsp; 브레이드 서버 였다네 ㅠ.   
  
  
&nbsp;