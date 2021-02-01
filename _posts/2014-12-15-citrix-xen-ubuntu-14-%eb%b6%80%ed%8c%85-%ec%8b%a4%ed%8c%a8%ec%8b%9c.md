---
title: citrix xen Ubuntu 14 부팅 실패시
author: netggio
layout: post
permalink: /archives/2307
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - Ubuntu
  - Ubuntu 14
  - xenserver
---
citrix Xen 템플릿이.. Ubuntu 12까지만 보인다.

12버전에서 .. 14버전으로 업데이트 하고 리부팅 하면.. 아래와 같은 메시지를 뿌리며.. 부팅 불가 발생 한다. 

Dec 15, 2014 10:51:18 AM Error: Starting VM &#8216;SERVER&#8217; &#8211; The bootloader for this VM returned an error &#8212; did the VM installation succeed? Unable to find partition containing kernel

해당 Xenserver의 /usr/lib/python2.4/site-packages/grub/GrubConf.py GrubConf.pl 파일 백업 후

/usr/lib/python2.4/site-packages/grub/GrubConf.py GrubConf.pl 파일을 수정 해주면 부팅 가능함.

if arg.strip() == &#8220;${saved_entry}&#8221;; 이부분을

if arg.strip() == &#8220;${saved\_entry}&#8221; or arg.strip() == &#8220;${next\_entry}&#8221;: 으로 변경함

업데이트한 우분트 정상 부팅 확인함.