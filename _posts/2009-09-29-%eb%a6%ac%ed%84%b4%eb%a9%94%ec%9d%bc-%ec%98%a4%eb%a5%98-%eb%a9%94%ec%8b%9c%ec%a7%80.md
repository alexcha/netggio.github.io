---
title: 리턴메일 오류 메시지
author: netggio
layout: post
permalink: /archives/1586
categories:
  - 일~일~일/etc
tags:
  - 메일 리턴메시지
---
리턴메일 오류 메시지

  


▶ 501 Denied domain name  
도메인주소를 잘못 입력 or 수신측에서 도메인을 수신거부한 경우 

  


▶ 421 Server too busy.  
수신측 서버의 응답지연. 수신서버의 트래픽등으로 메일을 수신 받지 못하는 상황에서 발송자에게 리턴 메일을 보냄.

  


▶ 421-Microsoft ESMTP MAIL Service, Version: 5.0.2195.5600 ready at Service not available, closing transmission channel  
MS사의 smtp 서버의 장애로 인해 메일을 수신받지 못하는 상황에서 리턴된 메시지. 

  


▶ 441 4.4.1 No answer from host  
수신측 서버의 응답이 없어서 리턴된 메시지. 

  


▶ 451 4.4.0 DNS resolving error  
수신측 서버의 도메인을 못찾아 리턴된 메시지. 

  


▶ 451 4.3.0 Other or undefined mail system status  
수신측 메일 시스템의 프로토콜이 틀리거나 수신 smtp 서버가 아닐경우 리턴되는 메시지. 

  


▶ 451 4.3.0 Temporary system failure. Please try again later.  
수신 서버의 일시적인 장애로 인해 메일을 수신받지 못해 리턴된 메시지. 

  


▶ 451 4.4.2 Bad connection (io timeout)  
수신 서버의 응답이 없어서 응답시간이 초과 되어 리턴된 메시지. 

  


▶ 451 Relay Server Not Ready.  
수신측 서버에서 릴레이 기능이 안돼어 리턴된 메시지. 

  


▶ 452 4.4.5 Insufficient disk space; try again later  
수신서버의 디스크용량이 부족하여 메일을 수신받지 못해 리턴된 메시지. 

  


▶ 500 Syntax Error, Command Unrecognized EHLO mail.example.com  
발송자의 메일 발송 클라이언트(Outlook등)에서 메일발송시 수신측 메일 서버에서   
SMTP 명령어를 인식하지 못해 리턴된 메시지. 

  


▶ 500 5.5.1 Command unrecognized: &#8220;XXXX mail.example.com&#8221;  
수신서버가 SMTP 명령어를 인식 하지 못함. (위와 동일).

  


▶ 501 5.1.8 Sender domain must exist(example.com)  
수신측 도메인(example.com) 이 존재 하지 않아 리턴된 메시지.

  


▶ 502 Not implemented  
수신측 서버가 smtp 명령어를 인식 하지 못해 리턴된 메시지. 

  


▶ 505 Authentication required  
수신측 서버가 릴레이 인증 등을 허용하지 않아 리턴된 메시지. 

  


▶ 512 5.1.2 Bad destination system address  
수신 서버의 장애나 네트웍 트래픽등으로 인헤 수신서버가 응답이 없을 때 리턴된 메시지. 

  


▶ 550 5.1.1 Suspended user <&example@example.com>>   
수신자의 사용자의 계정이 중단 상태.

  


▶ 550 5.1.2 <&example@example.com>>&#8230; Unsupported mail destination  
수신 서버가 응답이 지연되어 리턴된 메시지. 

  


▶ 550 5.7.1 <&example@example.com>>&#8230; Access denied.(211.202.13.144) <&example@example.com>>  
수신자(<example@example.com>)가 발신자의 메일주소를 수신 거부한 상태. 

  


▶ 550 5.7.1 <&example@example.com>>&#8230; Relaying denied. IP name lookup failed [211.115.203.111]  
수신 서버에서 발신자의 IP에 대해 릴레이 거부를 하여 메일을 보내지 못해 리턴된 메시지. 

  


▶ 550 Requested action not taken: mailbox unavailable  
수신자의 메일함을 찾지 못해 리턴된 메시지. 

  


▶ 550 Mail is reject ( filtering reject )  
수신 서버에서 발신자의 메일 주소나 IP를 필터링 하여 거부되어 리턴된 메시지. 

  


▶ 550 5.1.1 <&example@example.com>>&#8230; User unknown  
수신자 (<example@example.com>)계정을 찾지 못해 리턴된 메시지. 

  


▶ 550 5.7.1 Unable to relay for <example@example.com>  
수신 서버에서 릴레이 거부를 하여 리턴된 메시지. 

  


▶ 550 Invalid recipient <example@example.com>  
수신자 계정을 찾지 못해 리턴된 메시지 .

  


▶ 550 RCPT <&example@example.com>> ERROR. Mailbox doesn&#8217;t exist  
수신자 메일함이 존재 하지 않아서 리턴된 메시지. 

  


▶ 553 5.3.0 <&example@example.com>>&#8230; spam  
발송자의 계정이 수신서버 상에서 스패머로 등록이 되어 메일 수신 거부를 해서 리턴된 메시지 

  


▶ 553 sorry, your envelope sender is in my badmailfrom list  
발신자의 메일 주소가 수신서버상에서 블랙리스트에 올라 거부되어 리턴됨. 

  


▶ 553 sorry, that domain isn&#8217;t in my list of allowed rcpt hosts   
발신자의 메일 도메인주소 자체가 수신 서버에서 차단되어 리턴된 메시지. 

  


▶ 553 5.1.8 <&example@example.com>>&#8230; Domain of sender address <test@example.comdoes> not exist  
발신자의 도메인에 대해 수신서버에서 체크 하여 없는 도메인일 경우 리턴시킨 메시지. 

  


▶ 553 5.0.0 We do not accept mail from spammers &#8211; If you have questions,please email <example@example.com>  
발신자의 메일 계정이 스패머로 수신서버에서 등록이 되어 리턴된 메시지. 

  


▶ 553 sorry, your envelope sender is enlisted as spammer.  
발신자의 메일 주소가 수신서버상의 스패머 리스트에 등록 되어 리턴된 메시지. 

  


▶ 553-This target address is not our MX service  
수신자의 주소가 수신서버에서 서비스 안하는 도메인일 경우 리턴된 메시지. 

  


▶ 554 5.3.2 Rejected by mailbox host. REPLY:(250 <&example@example.com>>&#8230; Sender ok)  
수신자가 발송자의 메일 계정에 대해 수신 거부를 하여 리턴된 메시지 . 

  


▶ 554 5.3.0 Mail have traversed Too many hops. Reject it.  
발신자가 메일을 보낼 때 동보메일로 수신자의 메일 계정을 수신서버의 제한량 이상 넣어 보내어 리턴된 메시지. 

  


▶ 554 5.3.2 Rejected by mailbox host. REPLY:(550 5.1.1 unknown or illegal alias: <example@example.com>)  
수신자가 발송자의 메일 계정에 대해 수신거부를 설정하여 리턴된 메시지. 

  


▶ 554 1048035239.13309.hanmir accept failed. [code=-1]  
hanmir 서버에서 응답이 안돼어 리턴된 메시지.   
&nbsp;  
▶ 554 5.1.0 Sender Denied  
발신자의 계정을 수신서버에서 수신 거부함. 

  


▶ 554 <&example@example.com>>: Recipient address rejected: Access denied  
수신자가 발신자의 계정에 대해 수신 거부를 설정함