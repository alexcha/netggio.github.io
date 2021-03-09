---
title: CIFS client hang ㅡ.ㅡ;;
author: netggio
layout: post
permalink: /archives/1799
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - cifs
  - hang
---
<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  Unmounting CIFS filesystem: &nbsp; &nbsp; CIFS VFS: RFC1001 size 35 bigger than SMB for Mid=37884<BR />CIFS VFS: server not responding<BR />CIFS VFS: No response to cmd 116 mid 37884<BR />CIFS VFS: RFC1001 size 35 bigger than SMB for Mid=37837<BR />CIFS VFS: server not responding<BR />CIFS VFS: No response to cmd 116 mid 37837<BR />CIFS VFS: RFC1001 size 35 bigger than SMB for Mid=62586<BR />CIFS VFS: cifs_mount failed w/return code = -13
</DIV>

  
음.. REHL4 update8 에서 cifs로 &nbsp;natapp 언마운트시 위에 에러가 보이네..   
  
&nbsp;상위버전에 있는 netapp는 멀쩡하고.. 하위버전을 쓰고 있는 netapp만 그러는군&#8230;  
  
찾아보니 netapp 버그인가보다.. ㅡ.ㅡ;;   
  
[<INS><FONT color=#800080>http://kbase.redhat.com/faq/docs/DOC-17415</FONT></INS>][1]  
  
패치해줘야 하긴 해야 할건데 스토리지는 왠지 건들기가 ㅡ.ㅡ;  
  
dmesg 로그 올라오는거 짜증 스러운데쩝..  
  
</A>

 [1]: http://kbase.redhat.com/faq/docs/DOC-17415