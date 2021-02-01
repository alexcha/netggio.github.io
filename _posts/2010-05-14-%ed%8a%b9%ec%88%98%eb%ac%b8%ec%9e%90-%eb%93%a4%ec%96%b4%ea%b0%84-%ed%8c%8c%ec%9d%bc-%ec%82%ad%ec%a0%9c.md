---
title: 특수문자 들어간 파일 삭제
author: netggio
layout: post
permalink: /archives/1782
categories:
  - 일~일~일/linux
tags:
  - inode
  - 특수문자삭제
---
특수문자가 들어가서 파일을 삭제 할수 없을경우 inode를 찾아서 삭제 하면됨.

  


<DIV style="PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #e4e4e4; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; PADDING-TOP: 10px">
  # &nbsp;ls -i <BR />&nbsp;12345 test.txt&nbsp; 23456 ????test?.txt <BR /><BR /># find . -inum 23456 -exec rm -f {} \;
</DIV>