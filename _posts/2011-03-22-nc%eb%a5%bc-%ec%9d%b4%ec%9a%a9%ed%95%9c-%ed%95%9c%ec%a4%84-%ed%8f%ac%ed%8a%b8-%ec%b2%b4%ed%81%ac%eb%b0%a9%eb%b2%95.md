---
title: nc를 이용한 한줄 포트 체크방법.
author: netggio
layout: post
permalink: /archives/1952
categories:
  - 일~일~일/Script 모음
tags:
  - nc
  - 포트체크
---
nc를 이용한 초간단 포트 체크   
  
  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  /usr/bin/nc -z -w 1 google.com 80 ; { if [ &#8220;$?&#8221; -eq &#8220;0&#8221; ];&nbsp; then echo &#8220;ok&#8221;&nbsp; ;else echo &#8216;fail&#8217;; fi }
</DIV>