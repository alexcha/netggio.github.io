---
title: mutt를 이용한 첨부파일 메일 발송
author: netggio
layout: post
permalink: /archives/1672
categories:
  - 일~일~일/Script 모음
tags:
  - mail
  - mutt
  - 귀차니즘
  - 첨부파일
---
  
주기적으로 스케줄러를 통해 생성되는 결과물을 받아다가 담당자들에게 보내줘야 하는  
경우가 종종 있다.   
매우 귀찮은 일이 아닐수 없다 ㅋ&#8230;&nbsp; 담당자에게 ftp를 열어 주기도 그렇고.. &nbsp;매번 서버에들어가서.. 데이타를 받고,&nbsp; 또 다시 해당 담당자에게 메일을 보내고..&nbsp; 참 비효율적이다.. ㅠㅠ  
  
귀차니즘에서 벗어나는 방법은 나를 거치지 않고&nbsp; 해당 결과물을&nbsp; 담당자에게 보내는 방법이다 ㅋㅋ..&nbsp; email을 이용하는 방법 ㅎ.  
  
아래의 스크립트는 단순히 첨부파일을 첨부하여, 메일을 발송하는 스크립트다.  
  
쪼금 더 응용하여 각자 환경에 맞게..&nbsp; 귀차니즘에서 벗어나보자 ㅎ.  
  
  
필요한건  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; mutt에서 필요한건 mutt, mutt_dotlock 바이너리 파일  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; relay 허용된 smtp서버   
  
  
#########################################################################  
  


  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  #!/bin/bash<BR />#&nbsp; by netggio.pe.kr<BR /><BR />from_name=&#8221;Admin&#8221;<BR />from=&#8221;test<A href="mailto:test@netggio.pe.kr">@netggio.pe.kr</A>&#8220;<BR />to=&#8221;<A href="mailto:test@netggio.pe.kr">test@netggio.pe.kr</A>&#8220;<BR />subject=&#8221;TEST MAIL&#8221;<BR />smtp_server=&#8221;localhost&#8221;<BR />File=&#8221;test.zip&#8221;<BR />mesg=&#8221;test mesg&#8221;<BR />tools=&#8221;mutt_dotlock&#8221;&nbsp; <BR /><BR />./mutt -nx -e &#8216;set from=&#8217;$from&#8217;; set realname=&#8217;$from_name&#8217;; set dotlock_program=&#8217;$tools&#8217; ;set smtp_url=&#8221;smtp://&#8217;$smtp_server'&#8221;&#8216; -s &#8220;<BR />$subject&#8221; &#8220;$to&#8221; -a $File &nbsp;<< EOF<BR />$mesg<BR />EOF
</DIV>