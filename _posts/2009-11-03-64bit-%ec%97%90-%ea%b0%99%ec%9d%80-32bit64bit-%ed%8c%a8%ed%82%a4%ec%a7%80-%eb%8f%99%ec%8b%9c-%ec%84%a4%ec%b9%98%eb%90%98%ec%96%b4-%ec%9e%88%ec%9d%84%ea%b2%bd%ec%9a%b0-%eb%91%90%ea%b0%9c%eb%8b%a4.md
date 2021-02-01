---
title: '64bit 에  같은 32bit/64bit 패키지 동시 설치되어 있을경우 두개다 지우기.'
author: netggio
layout: post
permalink: /archives/1590
categories:
  - 일~일~일/linux
---
64bit 에&nbsp; 같은 32bit/64bit 패키지 동시 설치되어 있을경우 두개다 지우기.  
  
rpm -aq | grep mysql | xargs rpm -e  
  
rpm -aq | grep mysql | xargs rpm -e &#8211;nodeps &#8211;allmatches