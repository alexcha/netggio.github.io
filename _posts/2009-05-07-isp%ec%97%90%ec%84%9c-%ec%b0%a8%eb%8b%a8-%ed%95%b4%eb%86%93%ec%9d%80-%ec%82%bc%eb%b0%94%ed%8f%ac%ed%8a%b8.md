---
title: '집 <------> IDC 터널링 뚫기 ;;;'
author: netggio
layout: post
permalink: /archives/1577
categories:
  - Today Log
tags:
  - dd-wrt
  - GRE
  - sk브로드밴드
  - 삼바
  - 터널링
---
언제부터인지, 집에서 삼바 연결이 되질 않는다 ..  
  
분명히 집에서 잘 사용했었는데 ;;; &nbsp;&nbsp; 혹시 IDC에서 뭘 막아났나&#8230; 알아봐도 ㅡ.ㅡ;;;  
  
암것도 없단다&#8230; 사무실에선 잘되는걸 보니&#8230;&nbsp; 집쪽 인터넷 라인이 문제 ;;;;  
  
안되던 시점을 생각해보니&#8230; 하나로가 sk브로드밴드로 바뀌면서 부터인거 같다&#8230; ;;;  
  
아웃바운드도 막아 놓다니&#8230;&nbsp; 망할것들 ㅡ.ㅡ;;;   
&nbsp;  
귀찮아서 그냥 두고 있다가&#8230; 영 불편해서.. 어떻게 해보자는 생각이 들었다.  
  
가만 생각해보니,&nbsp; tomato 버전으로 핵펌 해놓은 링크시스 공유기가 보인다.. &nbsp;그거다&#8230; gre로 터널링을 하면  
  
돼겠다 싶어 공유기에 작업을 해보았더니.. GRE 모듈이 지원 안되는거 같다.. 젠장 ㅡ.ㅡ;;  
  
다른 핵펌 버전을 올려보았다.. DD-WRT ..&nbsp; 일전에 이 버전을 쓰다가.. 당나귀를 돌리면&#8230;  
  
인터넷이 느려지는 현상이 발생해서.. tomato로 갔었는데.. 시간도 지났으니.. 수정  
  
됐을거란 희망을 같고 올려봤다.. &nbsp; GRE모듈이 지원이 된다. ㅎㅎㅎ..  
  
오호 더욱~ &nbsp;쓸만한건. 공유기가 구동될때,&nbsp; 설정해놓은 스크립트를 돌아가게 할수 있다는게  
  
정말 유용한거 같다~.   
  
공유기에 GRE모듈을 올리고, IDC쪽 사설 만들고&#8230; 이것저것 바꾸고&#8230;.. ~~  
  
집과 IDC구간이 터널이 뚫렸다. ;;  
  
삼바 연결 성공 ;;; &nbsp; 오래된 공유기인데 이래저래~ 잘써먹는듯 하다~.  
  
이로써&#8230; 공유기를 킬때마다 집과 IDC 사이에 터널이 자동으로 생성되게 되었다  
  
집이 유동ip이니.. 바뀌게되면 한번씩 바꿔줘야 하는 귀차니즘이 발생하지만&#8230; 한달 이상 ip가  
  
바뀌지 않는걸 보면.. 그리 불편한건 없을거 같다.  
  
당나귀 돌아갈때 인터넷이 느려지거나 하는 현상은 없어 진듯 하다..