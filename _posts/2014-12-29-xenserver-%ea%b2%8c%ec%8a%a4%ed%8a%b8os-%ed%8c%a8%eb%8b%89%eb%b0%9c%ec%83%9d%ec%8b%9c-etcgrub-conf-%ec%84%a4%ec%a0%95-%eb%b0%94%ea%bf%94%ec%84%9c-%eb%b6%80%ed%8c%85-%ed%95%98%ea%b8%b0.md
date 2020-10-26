---
title: XenServer 게스트OS 패닉발생시 /etc/grub.conf 설정 바꿔서 부팅 하기.
author: netggio
layout: post
permalink: /archives/2313
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - citrix
  - grub
  - xen
  - 게스트OS 커널패닉
  - 커널패닉
---
커널업데이트 등으로.. 부팅 불가일 경우 boot화면에 커널을 바꿔서 부팅하면 되겠으나. Xenserver의 게스트 OS는 선택이 불가함..  
(되든가 ㅎ 기억이.. ㅋㅋ 암튼..)  
이런경우 버추얼호스트의 UUID를 확인해서 xen서버에서 다이렉트로 grub.conf 수정이 가능함

Xenserver 콘솔 진입 -> **xe-edit-bootloader -u 문제의 게스트OS UUID -p 1**  
위 방법으로 /etc/grub.conf를 수정 할수 있음 (콘솔은 pool에 묶어있는 xenserver 어느곳이라도 상관 없음)  
게스트 OS부팅해보면.. 선택한 커널로 부팅가능~