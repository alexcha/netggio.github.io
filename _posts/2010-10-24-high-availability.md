---
title: 'High availability &#8230;'
author: netggio
layout: post
permalink: /archives/1899
categories:
  - Today Log
tags:
  - High availability
  - 무정지
---
당연한 거겠지만&#8230; HA쪽에 눈이 많이 가게된다.. &nbsp;  
  
이런거 한다고 하면 .. 별아별 얘기가 다 나올게 뻔하다&#8230;. 돈들어간다.. 부터시작해서.. 잘돌아가는거.. 왜 건드냐&#8230; 등등.. 더 말안해도 무슨 얘긴지.. ㅋㅋㅋ 알듯.. 싶고.  
  
돈 안들이는 가정하에 .ㅋㅋ &nbsp; 열번 말하는거보다 한번 눈으로 보여주는게 빠르지&#8230; 않은가..  
  
지난주에 ipvsadm+keeplived&nbsp; 테스트 환경을 구축을 끝냈다.  
  
keeplived .. 귀찮을수 있는 ipvsadm의 컨트롤을 keeplived가 벗어나게 해준다.  
  
심오한(?) 테스트는 안직 해보지 않았지만 꽤 쓸만한 넘인건 분명한듯.  
  
DRDB +keeplived 구축할경우 active/active 가 가능 하다고 하는거 같다.  
  
우선 &nbsp;ipvsadm를 더 세세히 테스트 해본후 DRDB를 해봐야 겠다.  
  
ipvsadm은 조만간 실전에 투입 시켜볼 생각이다.&nbsp; 좀더 다양한 테스트 후에&#8230; ㅋㅋ..  
  
L4 보다야.. 좋을순 없겠지만..&nbsp; 비용 ㅋㅋ..  
  
  
음.. 해볼건 정말 무긍무진 한데&#8230; 문제는 이넘의 귀차니즘과&nbsp; 방해꾼들 ㅋㅋㅋ..  
  
HA시스템이 적재적소에서 정상 동작하고 있는날 내 손과 발이 편해진다는걸 생각하자 ㅋ