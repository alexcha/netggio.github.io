---
title: 미디어위키 패스워드 리셋
author: netggio
layout: post
permalink: /archives/1684
categories:
  - 일~일~일/etc
tags:
  - mediawiki
  - 미디어위키 패스워드 리셋
  - 패스워드 분실
---
오랜만에 위키 로그인 하려고 했더니만 패스워드 뭐였지&#8230;기역이 ㅠㅠ..  
  
아래의 방법으로 리셋 ;;;;;  
  
  
**[ DB에서 바로 리셋 방법 ]**  
  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  select user_id, user_name from user where user_name=&#8217;홍길동&#8217;;<BR />+&#8212;&#8212;&#8212;+&#8212;&#8212;&#8212;&#8211;+<BR />| user_id | user_name |<BR />+&#8212;&#8212;&#8212;+&#8212;&#8212;&#8212;&#8211;+<BR />| &nbsp; &nbsp;<STRONG><FONT color=#ff0000>10 </FONT></STRONG>&nbsp; &nbsp; &nbsp; |&nbsp; 홍길동 &nbsp; | <BR />+&#8212;&#8212;&#8212;+&#8212;&#8212;&#8212;&#8211;+<BR />1 row in set (0.00 sec)<BR /><BR />update user set user_password = MD5( CONCAT( user_id, &#8216;-&#8216;, MD5( &#8216;신규패스워드 &#8216; ) ) )&nbsp; where &nbsp;user_id = <FONT color=#ff0000><STRONG>10</STRONG> </FONT>;<BR />Query OK, 1 row affected (0.01 sec)<BR />Rows matched: 1&nbsp; Changed: 1&nbsp; Warnings: 0
</DIV>