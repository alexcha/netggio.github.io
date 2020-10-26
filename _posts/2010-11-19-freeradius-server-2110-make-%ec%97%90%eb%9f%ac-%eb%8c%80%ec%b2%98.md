---
title: freeradius-server-2.1.10 make 에러 대처.
author: netggio
layout: post
permalink: /archives/1901
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - freeradius
  - make error
---
freeradius-server-2.1.10 .. configure 하고 make 하면 에러 난다&#8230;. ㅡ.ㅡ;  
  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  .libs/radsniff.o(.text+0xe8b):/usr/loca/src/freeradius-server-2.1.10/src/main/radsniff.c:467: undefined reference to `pcap_fopen_offline&#8217;<BR />collect2: ld returned 1 exit status<BR />gmake[4]: *** [radsniff] Error 1<BR />gmake[4]: Leaving directory `/usr/local/src//freeradius-server-2.1.10/src/main&#8217;<BR />gmake[3]: *** [main] Error 2<BR />gmake[3]: Leaving directory `/usr/local/src/freeradius-server-2.1.10/src&#8217;<BR />gmake[2]: *** [all] Error 2<BR />gmake[2]: Leaving directory `/usr/local/src/freeradius-server-2.1.10/src&#8217;<BR />gmake[1]: *** [src] Error 2<BR />gmake[1]: Leaving directory `/usr/local/src/freeradius-server-2.1.10&#8242;<BR />make: *** [all] Error 2
</DIV>

  
이럴때..&nbsp; configure 하고 난후.. src/main/Makefile 열어서 아래의 부분 삭제   
<FONT style="BACKGROUND-COLOR: #e4e4e4"><br /> 

<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  BINARIES += radsniff
</DIV></FONT>

  
위 라인 삭제 후 make && make install   
  
에러없이 설치됨 ㅋ.