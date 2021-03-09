---
title: '[bash] 뒤섞인 ip 정렬'
author: netggio
layout: post
permalink: /archives/1823
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - bash
  - ip정렬
---
뒤썩인 ip 정렬 하기.

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  sh-3.00# cat ip.txt<BR />219.84.184.237<BR />123.232.233.1<BR />111.252.99.194<BR />61.62.169.154<BR />61.62.169.1<BR />222.12.1.4<BR />120.101.1.9<BR />131.29.9.1<BR /><BR />sh-3.00# &nbsp;<STRONG><FONT color=#ff0000>cat ip.txt | sort -n -t . -k 1,1 -k 2,2 -k 3,3 -k 4,4</FONT></STRONG><BR />61.62.169.1<BR />61.62.169.154<BR />111.252.99.194<BR />120.101.1.9<BR />123.232.233.1<BR />131.29.9.1<BR />219.84.184.237<BR />222.12.1.4<BR />sh-3.00#
</DIV>