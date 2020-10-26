---
title: mod_proxy 모듈 DSO 적재
author: netggio
layout: post
permalink: /archives/1589
categories:
  - 일~일~일/linux
---
mod_proxy 모듈 DSO 적재

  


proxy_util.c 가 필요하다. 안그러면   
  
apache/conf/httpd.conf: Cannot load /usr/local/apache/modules/mod\_proxy.so into server: /usr/local/apache/modules/mod\_proxy.so: undefined symbol: proxy\_lb\_workers  
위의 에러를 만나게 될것음  
  
  
해결책   
apxs -aic&nbsp; mod\_proxy\_http.c proxy_util.c  
apxs -aic&nbsp; mod\_proxy.c proxy\_util.c