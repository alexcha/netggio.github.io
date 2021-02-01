---
title: mod security 2.xx 버전에서 예외 처리 지시자
author: netggio
layout: post
permalink: /archives/1894
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - mod security
  - 예외처리
---
mod security 2.xx 버전에서 아래의 지시자를 ip혹은 도메인을 예외 처리를 할수 있다.  
  
IP 인 경우 &#8211;&nbsp; SecRule REMOTE_ADDR  
SecRule REMOTE_ADDR &#8220;192\.168\.1\.1&#8221; allow,ctl:ruleEngine=off  
  
도메인인 경우 &#8211; SecRule SERVER_NAME   
SecRule SERVER_NAME &#8220;blog\.netggio\.pe\.kr&#8221; allow,ctl:ruleEngine=off