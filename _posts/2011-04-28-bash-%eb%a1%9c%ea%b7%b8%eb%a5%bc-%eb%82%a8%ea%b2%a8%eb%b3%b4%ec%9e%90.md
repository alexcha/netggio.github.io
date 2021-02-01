---
title: 'bash  log/command log를 남기자~.'
author: netggio
layout: post
permalink: /archives/1955
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - bash
  - bash log
  - bash 패치
  - command 로그
---
언제나 보안 문제는 많았지만 ㅎ.. 최근에 H사 L사 땜시 큰 이슈이다..  
  
보안적인 측면 아니여도.. 다수가 접속하는 서버 같은경우,..&nbsp; 별아 별일이 다 있다..&nbsp;   
  
여기서의 최고봉은 ㅋㅋ 섭에서 사고쳐놓고 정작 본인은 잡아 때는거 아닐까? ㅋㅋ..  
  
접속자의 작업 실수로 생긴 문제라는.. &nbsp;분명한 심증은 있는데&#8230; ;;;  
  
물증이 없고, 이런저런 정황 증거뿐 ㅠ&#8230; ㅋㅋ  
  
어찌됐든.. &nbsp;물증 없는 사태 방지 하기위한 조치 사항 하나로 command 로그를 따로 남겨서 보관하는 방법이 있을거 같다.  
  
가장 쉬운 방법은 profile에 스크립트 넣어서 할수도 있다.. 근데 문제가좀있다 ㅋㅋ..  
그래서 skip..  
  
bash에 syslog 패치를 하는 방법에 있다. 이 방법이 좋을거 같다. 구글링해서 패치를 찾았다.. 정말 좋다 ㅎㅎ.&nbsp; . syslog가 되니 로그서버에 보관할수 있어 더 유용한거 같다.  
  
<https://github.com/mzupan/bash-paranoia-curl/blob/master/bash-paranoia.patch>  
  
&nbsp;접속을 시작으로 무슨 작업을 했는지 다 알수 있다~  
  
걸려봐라.. 물증이다~ ㅎㅎ..  
  
<img src="http://netggio.pe.kr/wp-content/uploads/1/7246702488.png" class="aligncenter" width="450" height="111" alt="사용자 삽입 이미지" />