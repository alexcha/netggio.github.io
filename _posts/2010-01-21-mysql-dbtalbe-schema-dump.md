---
title: '[mysql] DB/Talbe schema Dump'
author: netggio
layout: post
permalink: /archives/1615
categories:
  - 일~일~일/linux
tags:
  - mysql
  - schema Dump
---
[Mysql&nbsp; Schema Dump ]  
  
Table schema Dump  
mysqldump &#8211;default-character-set=캐릭터셋 -u root -p -d &#8211;opt DB명 Talbe명 >&nbsp; Table.dump

  


DB schema Dump  
mysqldump &#8211;default-character-set=캐릭터셋 -u root -p -d &#8211;opt &#8211;databases DB명 > DB.dump