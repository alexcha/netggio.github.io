---
title: puppet을 더욱 쉽게 해주는 foreman
author: netggio
layout: post
permalink: /archives/2224
categories:
  - Uncategorized
  - 일~일~일/OpenSource
tags:
  - foreman
  - puppet
  - Smart-Proxy
  - theforeman
  - 배포시스템
  - 자동화
  - 중앙관리
---
대규모 시스템에 중앙관리는 필수 아닌가&#8230; 그중에 쓸만한게 puppet아닐까 싶다.

puppet 엔터프라이즈는.. 상용이니.. 노드 제한이 있고.. 오픈소스 버전을 쓰자니.. 아쉬운게 너무 많다&#8230; 

특히.. puppet 오픈소스 버전에 puppet dashboard가 있으나.. 사용해 본 사람은 알겠지만.. 암울하다&#8230; 정말 ㅋㅋ

그러나 foreman에 puppet를 얻치면 엔터프라이즈 버전이 부럽지 않은 상태가 되된다~ ㅎㅎ. 누가 명칭 했는지 foreman 이름참.. 재밌네.. 로고도 ㅋㅋ 안전모야.. ㅋㅋ

![][1]

![][2]

![][3]

![][4]

http://theforeman.org

foreman은 puppet dashboard처럼 puppet 마스터서버와 연동 해주는 Smart-Proxy를 제공 해주고 있고, 웹에서 각 노드를 컨트롤 할수 있는 웹인터페이스를 제공 해주고 있다.  
현재 최신 rpm은 .. x86_64만 패키징 해났으므로.. centos6 64비트 OS기반에서 테스트 해보는게 맘편할듯.. 

1.3버전을 설치 해보았는데.. 아래의 기능들을 웹인터페이스에서 제공 해주고 있었다. 그밖에도 많은듯.. 한데 우선 내가 필요한거 기준으로 이틀 살펴본 결과

. 깔끔한 인터페이스  
. puppet Node 컨트롤 가능  
. 손쉬운 puppet Node 추가  
. 사이트 계정별 권한 부여 가능  
. 운영중이던 puppet의 마이그레이션 제공  
. 초간단 인스톨  
. 레포팅 제공  
. 손쉬운 인증서 관리  
. pueet class 관리 배포  
. 웹 vnc 제공  
. 모니터링

이것저것 테스트는 해보아야 하겠지만, 아직까지 매우 만족스럽다~ 이 모든게 오픈소스라니^^. 감솨할따름..

 [1]: http://theforeman.org/static/images/foreman.png
 [2]: http://theforeman.org/static/images/screenshots/hostpage.png
 [3]: http://theforeman.org/static/images/screenshots/host_listing.png
 [4]: http://theforeman.org/static/images/screenshots/hosteditpage.png