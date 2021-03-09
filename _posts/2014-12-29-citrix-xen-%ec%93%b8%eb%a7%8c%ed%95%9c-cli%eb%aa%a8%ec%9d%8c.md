---
title: 'citrix  xen 쓸만한 cli모음'
author: netggio
layout: post
permalink: /archives/2311
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - citrix
  - cli
  - xen
---
Xen콘솔은 xe 명령어를 기본으로 함.

CPU타입이 다른 Xenserver Pool로 묶는 방법  
xe pool-join force=true master-address=ip master-password=패스워드 master-username=root

강제로 CPU갯수 늘리기.. ( 게스트 win인경우.. 코어 늘린만큼.. core갯수 안나옴..해서.. 보여주기식으로 늘릴수는 있다&#8230;하지만 의미 있나? ㅡ.ㅡ..)  
xe vm-param-set platform:cores-per-socket=16 uuid=게스트OS UUID

Proxy를 이용해서 게스트OS 설치 할경우 프락시 설정  
xe vm-param-set uuid=게스트OS UUID other-config:install-proxy=http://프락시서버주소

게스트OS 리스트 보기(템플릿포함)  
xe vm-list

export 하기 -> (스냅샷으로 템플릿을 만든후 export해주면 됨)  
xe template-export template-uuid=템플릿UUID filename=win.xva

import 하기  
xe vm-import filename=centos6.4.xva sr-uuid=스토리지 UUID

&nbsp;

Xen 프로세스 ( 리눅스 -eq  top )

xentop -d 1