---
title: 'ulogd-1.24 ..  ulogd_MYSQL.so 생성 안되는 에러'
author: netggio
layout: post
permalink: /archives/1953
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - ulogd 에러
  - ulogd_MYSQL.so
---
&#8211;whti-mysql 옵션 추가해서 configure 후 make &nbsp;하게 되면 아래의 에러가 발생한다.  
  
  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  gcc -I-I/usr/include/mysql -DOLD_MYSQL=1&nbsp; -g -O2&nbsp; -Wall -DULOGD_CONFIGFILE=\&#8221;/usr/local/etc/ulogd.conf\&#8221; -I/lib/modules/`uname -r`/build/include -I.. -I../libipulog/include -I../include -fPIC -o ulogd_MYSQL_sh.o -c ulogd_MYSQL.c<BR />ld -shared -rdynamic -L/usr/lib/mysql -lmysqlclient -lz -lcrypt -lnsl -lm -lc -lnss_files -lnss_dns -lresolv -lc -lnss_files -lnss_dns -lresolv -lmygcc&nbsp; -o ulogd_MYSQL.so ulogd_MYSQL_sh.o -lc<BR />ld: bad -rpath option<BR />make[1]: *** [ulogd_MYSQL.so] Error 1<BR />make[1]: Leaving directory `/root/ulog/ulogd-1.24/mysql&#8217;<BR />make: *** [recurse] Error 1
</DIV>

  
configure 하면 Rules.make 파일이 생긴다.   
파일 오픈후   
  
  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  MYSQL_LDFLAGS= <STRONG><FONT color=#ff0000>-rdynamic</FONT><FONT color=#8e8e8e> </FONT><FONT color=#333333>&#8211;</FONT></STRONG><FONT color=#333333>L/</FONT>usr/lib/mysql -lmysqlclient -lz -lcrypt -lnsl -lm -lc -lnss_files -lnss_dns -lresolv -lc -lnss_files -l<BR />nss_dns -lresolv -lmygcc
</DIV>이부분에서

**&nbsp;<FONT color=#ff0000> -rdynamic</FONT>**<FONT color=#ff0000>&nbsp;</FONT> 삭제후 make 진행 하게 되면 문제 없이 ulogd_MYSQL.so 가 만들어지는게 보인다.