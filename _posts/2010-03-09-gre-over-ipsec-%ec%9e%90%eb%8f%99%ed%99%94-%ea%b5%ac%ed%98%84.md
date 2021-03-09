---
title: 'GRE over IPSec  터널링 자동화 구현'
author: netggio
layout: post
permalink: /archives/1710
categories:
  - '일~일~일/운영&amp;관리'
tags:
  - GRE
  - GRE over IPSec
  - ipsec
  - script
  - 귀차니즘
  - 보안
  - 자동화
  - 터널링
---
<img src="http://netggio.pe.kr/wp-content/uploads/1/1344878472.png" class="aligncenter" width="450" height="337" alt="사용자 삽입 이미지" />  
서로 다른 네트웍이 사설로 통신 해야&nbsp; 경우, 일반적으로&nbsp; gre터널링 방식을 많이 이용한다.

뭐 아닌경우도 있겠지만서도 ㅎ.&nbsp; 아무튼 개인적인 경우는 그렇다.

gre를 이용하는 이유는&nbsp; 그렇다.. 간단하니까 ㅋㅋ..

근데 여기서 문제가 생기는것이 보안적인 측면이다.&nbsp; 패킷이 암호화가 안된다는것..

해서..&nbsp; 결론은.. ipsec으로 암호화 터널을 뚫고, 그 안에 gre터널을 넣으면 되는것&#8230;

사실 예전부터 해야지 해야지 생각만 하다가 ㅋㅋㅋ.. 오늘에서야 문서를 완성 했다.

스크립트 만드는데 개고생 ;;;;;

차후에 또다 른 터널링을 할 경우를 대비해서 터널을 뚫고 난리를 치는 귀차니즘 방지용 으로

전구간 설정 자동화를 시켜났다.&nbsp; 설정 파일만 바꿔서 적용하면 끝. 귀차니즘에서 해방 ㅋㅋ  
&nbsp;  
자세한 설정 및 설명은 아래의 링크 참고.. ㅎ..

<a href="http://netggio.pe.kr/wiki/index.php/GRE%20over%20IPSec%20%EC%9E%90%EB%8F%99%ED%99%94%20%EA%B5%AC%ED%98%84" target="_blank"><font color="#0000ff" size="4">GRE over IPSec 자동화 구현 문서</font></a>