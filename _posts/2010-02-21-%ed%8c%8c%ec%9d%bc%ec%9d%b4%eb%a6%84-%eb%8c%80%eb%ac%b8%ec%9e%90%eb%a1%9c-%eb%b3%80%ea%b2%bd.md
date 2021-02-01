---
title: 파일이름 대문자로 변경
author: netggio
layout: post
permalink: /archives/1683
categories:
  - 일~일~일/Script 모음
tags:
  - 대소문자
  - 파일이름 변경
---
현재 폴더내의 파일이름을 모두 대문자로 바꾸는 스크립트.

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  <br /> 
  
  <P>
    #! /bin/bash
  </P>
  
  <br /> 
  
  <P>
    for filename in *<BR />do<BR />&nbsp; fname=`basename $filename`<BR />&nbsp; n=`echo $fname | tr A-Z a-z`<BR />&nbsp; if [ &#8220;$fname&#8221; != &#8220;$n&#8221; ]<BR />&nbsp; then<BR />&nbsp; &nbsp; mv $fname $n<BR />&nbsp; fi<BR />done
  </P>
  
  <br /> 
  
  <P>
    exit 0
  </P>
</DIV>