---
title: '[linux] 특정 파일들의 사이즈 연산'
author: netggio
layout: post
permalink: /archives/1911
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - awk
  - du
  - 합
---
특정 문자가 들어간 파일들의 크기를 다 더해서 합을 구해봐야 할거 같은데 ㅋㅋ  
  
파일들 넘 많아 ㅋㅋㅋㅋ   
  
du를 써서&#8230; 결과를 엑셀에 붙여넣기???  
  
설마 이런 노가다를???ㅋ  
  
du와 awk를 이용해서 한큐에&#8230;.  
  
  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  du -sm&nbsp; *특정문자열*&nbsp; | awk &#8216;{&nbsp; sum += $1 } END { print sum }&#8217;
</DIV>