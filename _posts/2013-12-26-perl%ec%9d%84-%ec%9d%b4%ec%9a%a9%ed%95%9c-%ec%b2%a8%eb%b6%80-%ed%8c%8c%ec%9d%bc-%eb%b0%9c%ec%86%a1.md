---
title: '파일 첨부하여 메일 전송 하기 &#8211; perl script'
author: netggio
layout: post
permalink: /archives/2262
categories:
  - 일~일~일/Script 모음
tags:
  - perl
  - script
  - 메일
  - 첨부파일 발송
---
외부 SMTP서버를 이용하여 첨부 파일을 보낼수 있는 간단한 스크립트

<pre class="brush:bash">#!/usr/bin/perl
use Encode;
use MIME::Lite;
use Net::SMTP;
use POSIX qw/strftime/;
use Time::Format qw(%time %strftime %manip);

#
my $YESTERDAY=$time{'yyyy/mm/dd', time-24*60*60};   # 하루전 날짜

#첨부파일 경로
my $REPORT=glob "/home/data/*.xlsx";

#첨부파일 유무 체크 -> 파일경로에 파일이 없으면 발송 하지 않음
if (-f $REPORT) {

#메일링 정보
 my $from_address = '발신지 메일 주소';
 
 my $to_address = '수신자 메일 주소';   # 구분은 콤마
 my $mail_host = 'SMTP 서버주소';

 my $subject = encode('MIME-Header',decode_utf8("$YESTERDAY - 테스트 메일"));   # 메일 제목
 my $message_body = "$YESTERDAY - 메시지 내용";   # 메시지 내용


my $msg = MIME::Lite->new (
   From => $from_address,
   To => $to_address,
   Subject => $subject,
   Type =>'multipart/mixed'
 ) or die "Error creating multipart container: $!\n";


$msg->attach (
   Type => 'TEXT',
   Data => $message_body
 ) or die "Error adding the text message part: $!\n";


 $msg->attach (
    Type => 'application/zip',
    Path => $REPORT,
    Disposition => 'attachment'
 ) or die "Error adding $REPORT: $!\n";

 MIME::Lite->send('smtp', $mail_host, Timeout=>60);
$msg->send;

# 발송후 첨부된 파일 삭제
unlink $REPORT;

}

else {

exit;
}


</pre>