---
title: 'mysql data  umask 적용법'
author: netggio
layout: post
permalink: /archives/1658
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - mysql
  - umask
---
mysql의 DATA의 DB폴더 같은 경우 디폴트로 700 이다.  
  
시스템을 운영하다보면 그룹에게 폴더 권한을 줘야 하는 경우가 종종생김&#8230;  
&nbsp;  
root 드릴테니 알아서 쓰세여 할수도 없고 ㅋㅋ 참으로 사람 귀찮게 함 ㅋㅋㅋ..  
  
db생성될때마다 권한 바꿔줄수도 없는 노릇이고 ㅎㅎㅎ. 귀차니즘 발생 ;;;  
  
이럴때 난 이런식으로 처리 했다. ;;;  
  
/etc/init.d/mysql 구동 스크립트 &nbsp;오픈 후 임의 적으로 umask 설정 해주면 된다.  
  
UMASK=504  
UMASK_DIR=504  
export UMASK  
export UMASK_DIR