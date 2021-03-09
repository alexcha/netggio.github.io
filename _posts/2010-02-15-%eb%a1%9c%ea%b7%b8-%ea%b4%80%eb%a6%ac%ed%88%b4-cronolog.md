---
title: 로그 관리툴 cronolog
author: netggio
layout: post
permalink: /archives/1648
categories:
  - 일~일~일/OpenSource
tags:
  - cronolog
  - 로그관리툴
---
<http://cronolog.org/>  
  
아파치 로그관리 할때 이용하는 로그툴이다.  
  
특징이라면 연/월/일 별로 폴더별 구분하여 로그를 저장시킬수 있다.  
  
**<FONT color=#0000ff>apache log 설정예 ></FONT>**  
ErrorLog &#8220;| /usr/local/cronolog/sbin/cronolog /usr/local/apache/logs/domain.error_log.%Y-%m-%d.log&#8221;  
CustomLog &#8220;| /usr/local/cronolog/sbin/cronolog /usr/local/apache/logs/domain.access_log.%Y-%m-%d.log&#8221;&nbsp; combine