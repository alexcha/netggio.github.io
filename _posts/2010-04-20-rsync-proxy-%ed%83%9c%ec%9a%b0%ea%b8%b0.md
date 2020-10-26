---
title: Rsync Proxy 태우기.
author: netggio
layout: post
permalink: /archives/1748
categories:
  - 일~일~일/Script 모음
tags:
  - proxy
  - rsync
---
  
사설 아이피만 가지고 있는 장비에서 외부로 데이타를 동기화하게 될일이 생길경우  
  
rsync의 프락시 옵션을 이용. 프락시를 태워서 보내면 됨..

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  #!/bin/bash<BR /><BR />PROXY_SERVER=&#8221;프락시서버 IP&#8221;<BR />DEST_SERVER=&#8221;목적지 IP&#8221;<BR />RSYNC_PROXY=$PROXY_SERVER<BR /><BR />export RSYNC_PROXY=$PROXY_SERVER<BR /><BR />rsync -avrz 동기화 할 디렉토리/* $DEST_SERVER::/동기화시킬 디렉토리<BR /><BR />
</DIV>