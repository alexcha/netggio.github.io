---
title: '[MySQL 5.1.4] /bin/rm: cannot remove `libtoolT&#8217;: No such file or directory'
author: netggio
layout: post
permalink: /archives/1612
categories:
  - 일~일~일/linux
tags:
  - "libtoolT': No such file or directory"
  - mysql5.1
---
mysql 5.1.X 설치시 아래의 문제에 봉착.  
  
/bin/rm: cannot remove \`libtoolT&#8217;: No such file or directory   
  
  
mysql 소스 디렉에서 아래와 같이 해주면 처리됨.  
  
autoreconf &#8211;force &#8211;install  
aclocal  
libtoolize &#8211;automake &#8211;force  
automake &#8211;force &#8211;add-missing  
  
그리고 나서 &nbsp;config&#8230; 해보면 말끔이 사라졌을거임. ㅎ  
&nbsp;   
CFLAGS=&#8221;-O3&#8243; CXX=gcc CXXFLAGS=&#8221;-O3 -felide-constructors -fno-exceptions -fno-rtti&#8221;