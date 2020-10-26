---
title: Apache 모듈 목록
author: netggio
layout: post
permalink: /archives/1588
categories:
  - 일~일~일/linux
tags:
  - apache
  - module
---
<H2 class=section>[<U><FONT color=#0000ff>core</FONT></U>][1] </H2>  
<DIV class=section>  


  

:   Core Apache HTTP Server features that are always available  
    
    
    [<U><FONT color=#0000ff>mpm_common</FONT></U>][2]  
    <DD class=separate>A collection of directives that are implemented by more than one multi-processing module (MPM)  
    
    
    [<U><FONT color=#0000ff>beos</FONT></U>][3]  
    
    
    :   BeOS에 최적화된 다중처리 모듈.  
        
        
        [<U><FONT color=#0000ff>event</FONT></U>][4]  
        
        
        :   An experimental variant of the standard <CODE class=module>[<U><FONT color=#0000ff>worker</FONT></U>][5]</CODE> MPM  
            
            
            [<U><FONT color=#0000ff>mpm_netware</FONT></U>][6]  
            
            
            :   Multi-Processing Module implementing an exclusively threaded web server optimized for Novell NetWare  
                
                
                [<U><FONT color=#0000ff>mpmt_os2</FONT></U>][7]  
                
                
                :   Hybrid multi-process, multi-threaded MPM for OS/2  
                    
                    
                    [<U><FONT color=#0000ff>prefork</FONT></U>][8]  
                    
                    
                    :   Implements a non-threaded, pre-forking web server  
                        
                        
                        [<U><FONT color=#0000ff>mpm_winnt</FONT></U>][9]  
                        
                        
                        :   This Multi-Processing Module is optimized for Windows NT.  
                            
                            
                            [<U><FONT color=#0000ff>worker</FONT></U>][5]  
                            
                            
                            :   Multi-Processing Module implementing a hybrid multi-threaded multi-process web server </DL></DIV>
                              
                            <DIV class=top>  
                            &nbsp;</DIV>  
                            <DIV class=section>  
                            
                            
                              
                            
                            
                            <A id=A href="http://httpd.apache.org/docs/2.2/ko/mod/mod_actions.html" name=A><U><FONT color=#0000ff>mod_actions</FONT></U></A>  
                            
                            
                            :   이 모듈은 미디어종류나 요청메서드에 따라 CGI 스크립트를 실행한다.  
                                
                                
                                [<U><FONT color=#0000ff>mod_alias</FONT></U>][10]  
                                
                                
                                :   파일시스템의 다른 부분들을 문서 계층구조에 포함하고, URL 리다이렉션을 제공한다  
                                    
                                    
                                    [<U><FONT color=#0000ff>mod_asis</FONT></U>][11]  
                                    
                                    
                                    :   HTTP 헤더를 포함한 파일을 보낸다  
                                        
                                        
                                        [<U><FONT color=#0000ff>mod\_auth\_basic</FONT></U>][12]  
                                        
                                        
                                        :   Basic authentication  
                                            
                                            
                                            [<U><FONT color=#0000ff>mod\_auth\_digest</FONT></U>][13]  
                                            
                                            
                                            :   MD5 Digest Authentication을 사용한 사용자인증.  
                                                
                                                
                                                [<U><FONT color=#0000ff>mod\_authn\_alias</FONT></U>][14]  
                                                
                                                
                                                :   Provides the ability to create extended authentication providers based on actual providers  
                                                    
                                                    
                                                    [<U><FONT color=#0000ff>mod\_authn\_anon</FONT></U>][15]  
                                                    
                                                    
                                                    :   인증영역에 &#8220;익명(anonymous)&#8221; 사용자의 접근을 허용한다  
                                                        
                                                        
                                                        [<U><FONT color=#0000ff>mod\_authn\_dbd</FONT></U>][16]  
                                                        
                                                        
                                                        :   User authentication using an SQL database  
                                                            
                                                            
                                                            [<U><FONT color=#0000ff>mod\_authn\_dbm</FONT></U>][17]  
                                                            
                                                            
                                                            :   DBM 파일을 사용한 사용자 인증  
                                                                
                                                                
                                                                [<U><FONT color=#0000ff>mod\_authn\_default</FONT></U>][18]  
                                                                
                                                                
                                                                :   최후 인증모듈  
                                                                    
                                                                    
                                                                    [<U><FONT color=#0000ff>mod\_authn\_file</FONT></U>][19]  
                                                                    
                                                                    
                                                                    :   문자파일을 이용한 사용자 인증  
                                                                        
                                                                        
                                                                        [<U><FONT color=#0000ff>mod\_authnz\_ldap</FONT></U>][20]  
                                                                        
                                                                        
                                                                        :   Allows an LDAP directory to be used to store the database for HTTP Basic authentication.  
                                                                            
                                                                            
                                                                            [<U><FONT color=#0000ff>mod\_authz\_dbm</FONT></U>][21]  
                                                                            
                                                                            
                                                                            :   DBM 파일을 사용한 그룹 인증  
                                                                                
                                                                                
                                                                                [<U><FONT color=#0000ff>mod\_authz\_default</FONT></U>][22]  
                                                                                
                                                                                
                                                                                :   최후 권한부여모듈  
                                                                                    
                                                                                    
                                                                                    [<U><FONT color=#0000ff>mod\_authz\_groupfile</FONT></U>][23]  
                                                                                    
                                                                                    
                                                                                    :   일반 문자파일을 이용한 그룹 권한부여  
                                                                                        
                                                                                        
                                                                                        [<U><FONT color=#0000ff>mod\_authz\_host</FONT></U>][24]  
                                                                                        
                                                                                        
                                                                                        :   호스트 (이름이나 IP 주소)를 사용한 그룹 권한부여  
                                                                                            
                                                                                            
                                                                                            [<U><FONT color=#0000ff>mod\_authz\_owner</FONT></U>][25]  
                                                                                            
                                                                                            
                                                                                            :   파일 소유자를 이용한 권한부여  
                                                                                                
                                                                                                
                                                                                                [<U><FONT color=#0000ff>mod\_authz\_user</FONT></U>][26]  
                                                                                                
                                                                                                
                                                                                                :   사용자 권한부여  
                                                                                                    
                                                                                                    
                                                                                                    [<U><FONT color=#0000ff>mod_autoindex</FONT></U>][27]  
                                                                                                    
                                                                                                    
                                                                                                    :   자동으로 유닉스의 `ls` 명령어나 Win32의 `dir` 쉘명령어와 유사한 디렉토리 목록을 만든다  
                                                                                                        
                                                                                                        
                                                                                                        <A id=C href="http://httpd.apache.org/docs/2.2/ko/mod/mod_cache.html" name=C><U><FONT color=#0000ff>mod_cache</FONT></U></A>  
                                                                                                        
                                                                                                        
                                                                                                        :   URI를 키로 사용하여 내용을 캐쉬한다.  
                                                                                                            
                                                                                                            
                                                                                                            [<U><FONT color=#0000ff>mod\_cern\_meta</FONT></U>][28]  
                                                                                                            
                                                                                                            
                                                                                                            :   CERN 웹서버 메타파일 지원  
                                                                                                                
                                                                                                                
                                                                                                                [<U><FONT color=#0000ff>mod_cgi</FONT></U>][29]  
                                                                                                                
                                                                                                                
                                                                                                                :   CGI 스크립트 실행  
                                                                                                                    
                                                                                                                    
                                                                                                                    [<U><FONT color=#0000ff>mod_cgid</FONT></U>][30]  
                                                                                                                    
                                                                                                                    
                                                                                                                    :   외부 CGI 데몬을 사용하여 CGI 스크립트를 실행  
                                                                                                                        
                                                                                                                        
                                                                                                                        [<U><FONT color=#0000ff>mod\_charset\_lite</FONT></U>][31]  
                                                                                                                        
                                                                                                                        
                                                                                                                        :   문자집합 변환을 지정  
                                                                                                                            
                                                                                                                            
                                                                                                                            <A id=D href="http://httpd.apache.org/docs/2.2/ko/mod/mod_dav.html" name=D><U><FONT color=#0000ff>mod_dav</FONT></U></A>  
                                                                                                                            
                                                                                                                            
                                                                                                                            :   Distributed Authoring and Versioning ([<U><FONT color=#0000ff>WebDAV</FONT></U>][32]) 기능  
                                                                                                                                
                                                                                                                                
                                                                                                                                [<U><FONT color=#0000ff>mod\_dav\_fs</FONT></U>][33]  
                                                                                                                                
                                                                                                                                
                                                                                                                                :   <CODE class=module>[<U><FONT color=#0000ff>mod_dav</FONT></U>][34]</CODE>을 위한 파일시스템 제공자  
                                                                                                                                    
                                                                                                                                    
                                                                                                                                    [<U><FONT color=#0000ff>mod\_dav\_lock</FONT></U>][35]  
                                                                                                                                    
                                                                                                                                    
                                                                                                                                    :   generic locking module for <CODE class=module>[<U><FONT color=#0000ff>mod_dav</FONT></U>][34]</CODE>  
                                                                                                                                        
                                                                                                                                        
                                                                                                                                        [<U><FONT color=#0000ff>mod_dbd</FONT></U>][36]  
                                                                                                                                        
                                                                                                                                        
                                                                                                                                        :   Manages SQL database connections  
                                                                                                                                            
                                                                                                                                            
                                                                                                                                            [<U><FONT color=#0000ff>mod_deflate</FONT></U>][37]  
                                                                                                                                            
                                                                                                                                            
                                                                                                                                            :   내용을 클라이언트로 보내기 전에 압축한다  
                                                                                                                                                
                                                                                                                                                
                                                                                                                                                [<U><FONT color=#0000ff>mod_dir</FONT></U>][38]  
                                                                                                                                                
                                                                                                                                                
                                                                                                                                                :   &#8220;마지막 슬래쉬&#8221; 리다이렉션을 제공하고 디렉토리 index 파일을 서비스한다  
                                                                                                                                                    
                                                                                                                                                    
                                                                                                                                                    [<U><FONT color=#0000ff>mod\_disk\_cache</FONT></U>][39]  
                                                                                                                                                    
                                                                                                                                                    
                                                                                                                                                    :   Content cache storage manager keyed to URIs  
                                                                                                                                                        
                                                                                                                                                        
                                                                                                                                                        [<U><FONT color=#0000ff>mod_dumpio</FONT></U>][40]  
                                                                                                                                                        
                                                                                                                                                        
                                                                                                                                                        :   Dumps all I/O to error log as desired.  
                                                                                                                                                            
                                                                                                                                                            
                                                                                                                                                            <A id=E href="http://httpd.apache.org/docs/2.2/ko/mod/mod_echo.html" name=E><U><FONT color=#0000ff>mod_echo</FONT></U></A>  
                                                                                                                                                            
                                                                                                                                                            
                                                                                                                                                            :   프로토콜 모듈을 설명하기위한 간단한 echo 서버  
                                                                                                                                                                
                                                                                                                                                                
                                                                                                                                                                [<U><FONT color=#0000ff>mod_env</FONT></U>][41]  
                                                                                                                                                                
                                                                                                                                                                
                                                                                                                                                                :   CGI 스크립트나 SSI 페이지에 전달할 환경변수를 수정한다  
                                                                                                                                                                    
                                                                                                                                                                    
                                                                                                                                                                    [<U><FONT color=#0000ff>mod_example</FONT></U>][42]  
                                                                                                                                                                    
                                                                                                                                                                    
                                                                                                                                                                    :   아파치 모듈 API를 설명한다  
                                                                                                                                                                        
                                                                                                                                                                        
                                                                                                                                                                        [<U><FONT color=#0000ff>mod_expires</FONT></U>][43]  
                                                                                                                                                                        
                                                                                                                                                                        
                                                                                                                                                                        :   사용자가 지정한 기준에 따라 `Expires`와 `Cache-Control` HTTP 헤더를 생성한다  
                                                                                                                                                                            
                                                                                                                                                                            
                                                                                                                                                                            [<U><FONT color=#0000ff>mod\_ext\_filter</FONT></U>][44]  
                                                                                                                                                                            
                                                                                                                                                                            
                                                                                                                                                                            :   응답 내용을 외부 프로그램으로 처리한 후 클라이언트로 보낸다  
                                                                                                                                                                                
                                                                                                                                                                                
                                                                                                                                                                                <A id=F href="http://httpd.apache.org/docs/2.2/ko/mod/mod\_file\_cache.html" name=F><U><FONT color=#0000ff>mod\_file\_cache</FONT></U></A>  
                                                                                                                                                                                
                                                                                                                                                                                
                                                                                                                                                                                :   메모리에 정적 파일들을 캐쉬  
                                                                                                                                                                                    
                                                                                                                                                                                    
                                                                                                                                                                                    [<U><FONT color=#0000ff>mod_filter</FONT></U>][45]  
                                                                                                                                                                                    
                                                                                                                                                                                    
                                                                                                                                                                                    :   Context-sensitive smart filter configuration module  
                                                                                                                                                                                        
                                                                                                                                                                                        
                                                                                                                                                                                        <A id=H href="http://httpd.apache.org/docs/2.2/ko/mod/mod_headers.html" name=H><U><FONT color=#0000ff>mod_headers</FONT></U></A>  
                                                                                                                                                                                        
                                                                                                                                                                                        
                                                                                                                                                                                        :   HTTP 요청 헤더와 응답 헤더 수정  
                                                                                                                                                                                            
                                                                                                                                                                                            
                                                                                                                                                                                            <A id=I href="http://httpd.apache.org/docs/2.2/ko/mod/mod_ident.html" name=I><U><FONT color=#0000ff>mod_ident</FONT></U></A>  
                                                                                                                                                                                            
                                                                                                                                                                                            
                                                                                                                                                                                            :   RFC 1413 ident 검색  
                                                                                                                                                                                                
                                                                                                                                                                                                
                                                                                                                                                                                                [<U><FONT color=#0000ff>mod_imagemap</FONT></U>][46]  
                                                                                                                                                                                                
                                                                                                                                                                                                
                                                                                                                                                                                                :   서버측 이미지맵(imagemap) 처리  
                                                                                                                                                                                                    
                                                                                                                                                                                                    
                                                                                                                                                                                                    [<U><FONT color=#0000ff>mod_include</FONT></U>][47]  
                                                                                                                                                                                                    
                                                                                                                                                                                                    
                                                                                                                                                                                                    :   Server-parsed html documents (Server Side Includes)  
                                                                                                                                                                                                        
                                                                                                                                                                                                        
                                                                                                                                                                                                        [<U><FONT color=#0000ff>mod_info</FONT></U>][48]  
                                                                                                                                                                                                        
                                                                                                                                                                                                        
                                                                                                                                                                                                        :   서버 설정에 대한 종합적인 정보를 보여준다  
                                                                                                                                                                                                            
                                                                                                                                                                                                            
                                                                                                                                                                                                            [<U><FONT color=#0000ff>mod_isapi</FONT></U>][49]  
                                                                                                                                                                                                            
                                                                                                                                                                                                            
                                                                                                                                                                                                            :   Windows용 아파치에서 ISAPI Extension 사용  
                                                                                                                                                                                                                
                                                                                                                                                                                                                
                                                                                                                                                                                                                <A id=L href="http://httpd.apache.org/docs/2.2/ko/mod/mod_ldap.html" name=L><U><FONT color=#0000ff>mod_ldap</FONT></U></A>  
                                                                                                                                                                                                                
                                                                                                                                                                                                                
                                                                                                                                                                                                                :   LDAP connection pooling and result caching services for use by other LDAP modules  
                                                                                                                                                                                                                    
                                                                                                                                                                                                                    
                                                                                                                                                                                                                    [<U><FONT color=#0000ff>mod\_log\_config</FONT></U>][50]  
                                                                                                                                                                                                                    
                                                                                                                                                                                                                    
                                                                                                                                                                                                                    :   서버로의 요청을 로그에 기록한다  
                                                                                                                                                                                                                        
                                                                                                                                                                                                                        
                                                                                                                                                                                                                        [<U><FONT color=#0000ff>mod\_log\_forensic</FONT></U>][51]  
                                                                                                                                                                                                                        
                                                                                                                                                                                                                        
                                                                                                                                                                                                                        :   Forensic Logging of the requests made to the server  
                                                                                                                                                                                                                            
                                                                                                                                                                                                                            
                                                                                                                                                                                                                            [<U><FONT color=#0000ff>mod_logio</FONT></U>][52]  
                                                                                                                                                                                                                            
                                                                                                                                                                                                                            
                                                                                                                                                                                                                            :   요청당 입출력 바이트수를 기록  
                                                                                                                                                                                                                                
                                                                                                                                                                                                                                
                                                                                                                                                                                                                                <A id=M href="http://httpd.apache.org/docs/2.2/ko/mod/mod\_mem\_cache.html" name=M><U><FONT color=#0000ff>mod\_mem\_cache</FONT></U></A>  
                                                                                                                                                                                                                                
                                                                                                                                                                                                                                
                                                                                                                                                                                                                                :   URI를 키로 사용하여 내용을 캐쉬한다.  
                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                    [<U><FONT color=#0000ff>mod_mime</FONT></U>][53]  
                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                    :   Associates the requested filename&#8217;s extensions with the file&#8217;s behavior (handlers and filters) and content (mime-type, language, character set and encoding)  
                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                        [<U><FONT color=#0000ff>mod\_mime\_magic</FONT></U>][54]  
                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                        :   Determines the MIME type of a file by looking at a few bytes of its contents  
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            <A id=N href="http://httpd.apache.org/docs/2.2/ko/mod/mod_negotiation.html" name=N><U><FONT color=#0000ff>mod_negotiation</FONT></U></A>  
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            :   Provides for [<U><FONT color=#0000ff>content negotiation</FONT></U>][55]  
                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                [<U><FONT color=#0000ff>mod\_nw\_ssl</FONT></U>][56]  
                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                :   Enable SSL encryption for NetWare  
                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                    <A id=P href="http://httpd.apache.org/docs/2.2/ko/mod/mod_proxy.html" name=P><U><FONT color=#0000ff>mod_proxy</FONT></U></A>  
                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                    :   HTTP/1.1 proxy/gateway server  
                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                        [<U><FONT color=#0000ff>mod\_proxy\_ajp</FONT></U>][57]  
                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                        :   AJP support module for <CODE class=module>[<U><FONT color=#0000ff>mod_proxy</FONT></U>][58]</CODE>  
                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                            [<U><FONT color=#0000ff>mod\_proxy\_balancer</FONT></U>][59]  
                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                            :   <CODE class=module>[<U><FONT color=#0000ff>mod_proxy</FONT></U>][58]</CODE> extension for load balancing  
                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                [<U><FONT color=#0000ff>mod\_proxy\_connect</FONT></U>][60]  
                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                :   <CODE class=module>[<U><FONT color=#0000ff>mod_proxy</FONT></U>][58]</CODE> extension for `CONNECT` request handling  
                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                    [<U><FONT color=#0000ff>mod\_proxy\_ftp</FONT></U>][61]  
                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                    :   FTP support module for <CODE class=module>[<U><FONT color=#0000ff>mod_proxy</FONT></U>][58]</CODE>  
                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                        [<U><FONT color=#0000ff>mod\_proxy\_http</FONT></U>][62]  
                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                        :   HTTP support module for <CODE class=module>[<U><FONT color=#0000ff>mod_proxy</FONT></U>][58]</CODE>  
                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                            [<U><FONT color=#0000ff>mod\_proxy\_scgi</FONT></U>][63]  
                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                            :   SCGI gateway module for <CODE class=module>[<U><FONT color=#0000ff>mod_proxy</FONT></U>][58]</CODE>  
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                <A id=R href="http://httpd.apache.org/docs/2.2/ko/mod/mod_rewrite.html" name=R><U><FONT color=#0000ff>mod_rewrite</FONT></U></A>  
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                :   Provides a rule-based rewriting engine to rewrite requested URLs on the fly  
                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                    <A id=S href="http://httpd.apache.org/docs/2.2/ko/mod/mod_setenvif.html" name=S><U><FONT color=#0000ff>mod_setenvif</FONT></U></A>  
                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                    :   요청의 성격에 따라 환경변수 설정을 변경한다  
                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                        [<U><FONT color=#810081>mod_so</FONT></U>][64]  
                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                        :   시작할때 혹은 재시작할때 실행가능한 코드와 모듈을 서버로 읽어들인다  
                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                            [<U><FONT color=#0000ff>mod_speling</FONT></U>][65]  
                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                            :   사용자가 대소문자를 잘못 사용하거나 맞춤법이 틀리는 것을 한번까지 허용하여 잘못된 URL을 고치려고 시도한다  
                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                [<U><FONT color=#0000ff>mod_ssl</FONT></U>][66]  
                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                :   Strong cryptography using the Secure Sockets Layer (SSL) and Transport Layer Security (TLS) protocols  
                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                    [<U><FONT color=#0000ff>mod_status</FONT></U>][67]  
                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                    :   서버 활동과 성능에 대한 정보를 제공한다  
                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                        [<U><FONT color=#0000ff>mod_substitute</FONT></U>][68]  
                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                        :   Perform search and replace operations on response bodies  
                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                            [<U><FONT color=#0000ff>mod_suexec</FONT></U>][69]  
                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                            :   CGI 스크립트를 특정 사용자와 그룹 권한으로 실행한다  
                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                <A id=U href="http://httpd.apache.org/docs/2.2/ko/mod/mod\_unique\_id.html" name=U><U><FONT color=#0000ff>mod\_unique\_id</FONT></U></A>  
                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                :   각 요청마다 유일한 식별자를 가지는 환경변수를 제공한다  
                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                    [<U><FONT color=#0000ff>mod_userdir</FONT></U>][70]  
                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                    :   사용자별 디렉토리  
                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                        [<U><FONT color=#0000ff>mod_usertrack</FONT></U>][71]  
                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                        :   *Clickstream* logging of user activity on a site  
                                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                            <A id=V href="http://httpd.apache.org/docs/2.2/ko/mod/mod_version.html" name=V><U><FONT color=#0000ff>mod_version</FONT></U></A>  
                                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                            :   버전별 설정  
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                [<U><FONT color=#0000ff>mod\_vhost\_alias</FONT></U>][72]  
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                :   Provides for dynamically configured mass virtual hosting </DL></DIV></p>

 [1]: http://httpd.apache.org/docs/2.2/ko/mod/core.html
 [2]: http://httpd.apache.org/docs/2.2/ko/mod/mpm_common.html
 [3]: http://httpd.apache.org/docs/2.2/ko/mod/beos.html
 [4]: http://httpd.apache.org/docs/2.2/ko/mod/event.html
 [5]: http://httpd.apache.org/docs/2.2/ko/mod/worker.html
 [6]: http://httpd.apache.org/docs/2.2/ko/mod/mpm_netware.html
 [7]: http://httpd.apache.org/docs/2.2/ko/mod/mpmt_os2.html
 [8]: http://httpd.apache.org/docs/2.2/ko/mod/prefork.html
 [9]: http://httpd.apache.org/docs/2.2/ko/mod/mpm_winnt.html
 [10]: http://httpd.apache.org/docs/2.2/ko/mod/mod_alias.html
 [11]: http://httpd.apache.org/docs/2.2/ko/mod/mod_asis.html
 [12]: http://httpd.apache.org/docs/2.2/ko/mod/mod_auth_basic.html
 [13]: http://httpd.apache.org/docs/2.2/ko/mod/mod_auth_digest.html
 [14]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authn_alias.html
 [15]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authn_anon.html
 [16]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authn_dbd.html
 [17]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authn_dbm.html
 [18]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authn_default.html
 [19]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authn_file.html
 [20]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authnz_ldap.html
 [21]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authz_dbm.html
 [22]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authz_default.html
 [23]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authz_groupfile.html
 [24]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authz_host.html
 [25]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authz_owner.html
 [26]: http://httpd.apache.org/docs/2.2/ko/mod/mod_authz_user.html
 [27]: http://httpd.apache.org/docs/2.2/ko/mod/mod_autoindex.html
 [28]: http://httpd.apache.org/docs/2.2/ko/mod/mod_cern_meta.html
 [29]: http://httpd.apache.org/docs/2.2/ko/mod/mod_cgi.html
 [30]: http://httpd.apache.org/docs/2.2/ko/mod/mod_cgid.html
 [31]: http://httpd.apache.org/docs/2.2/ko/mod/mod_charset_lite.html
 [32]: http://www.webdav.org/
 [33]: http://httpd.apache.org/docs/2.2/ko/mod/mod_dav_fs.html
 [34]: http://httpd.apache.org/docs/2.2/ko/mod/mod_dav.html
 [35]: http://httpd.apache.org/docs/2.2/ko/mod/mod_dav_lock.html
 [36]: http://httpd.apache.org/docs/2.2/ko/mod/mod_dbd.html
 [37]: http://httpd.apache.org/docs/2.2/ko/mod/mod_deflate.html
 [38]: http://httpd.apache.org/docs/2.2/ko/mod/mod_dir.html
 [39]: http://httpd.apache.org/docs/2.2/ko/mod/mod_disk_cache.html
 [40]: http://httpd.apache.org/docs/2.2/ko/mod/mod_dumpio.html
 [41]: http://httpd.apache.org/docs/2.2/ko/mod/mod_env.html
 [42]: http://httpd.apache.org/docs/2.2/ko/mod/mod_example.html
 [43]: http://httpd.apache.org/docs/2.2/ko/mod/mod_expires.html
 [44]: http://httpd.apache.org/docs/2.2/ko/mod/mod_ext_filter.html
 [45]: http://httpd.apache.org/docs/2.2/ko/mod/mod_filter.html
 [46]: http://httpd.apache.org/docs/2.2/ko/mod/mod_imagemap.html
 [47]: http://httpd.apache.org/docs/2.2/ko/mod/mod_include.html
 [48]: http://httpd.apache.org/docs/2.2/ko/mod/mod_info.html
 [49]: http://httpd.apache.org/docs/2.2/ko/mod/mod_isapi.html
 [50]: http://httpd.apache.org/docs/2.2/ko/mod/mod_log_config.html
 [51]: http://httpd.apache.org/docs/2.2/ko/mod/mod_log_forensic.html
 [52]: http://httpd.apache.org/docs/2.2/ko/mod/mod_logio.html
 [53]: http://httpd.apache.org/docs/2.2/ko/mod/mod_mime.html
 [54]: http://httpd.apache.org/docs/2.2/ko/mod/mod_mime_magic.html
 [55]: http://httpd.apache.org/docs/2.2/ko/content-negotiation.html
 [56]: http://httpd.apache.org/docs/2.2/ko/mod/mod_nw_ssl.html
 [57]: http://httpd.apache.org/docs/2.2/ko/mod/mod_proxy_ajp.html
 [58]: http://httpd.apache.org/docs/2.2/ko/mod/mod_proxy.html
 [59]: http://httpd.apache.org/docs/2.2/ko/mod/mod_proxy_balancer.html
 [60]: http://httpd.apache.org/docs/2.2/ko/mod/mod_proxy_connect.html
 [61]: http://httpd.apache.org/docs/2.2/ko/mod/mod_proxy_ftp.html
 [62]: http://httpd.apache.org/docs/2.2/ko/mod/mod_proxy_http.html
 [63]: http://httpd.apache.org/docs/2.2/ko/mod/mod_proxy_scgi.html
 [64]: http://httpd.apache.org/docs/2.2/ko/mod/mod_so.html
 [65]: http://httpd.apache.org/docs/2.2/ko/mod/mod_speling.html
 [66]: http://httpd.apache.org/docs/2.2/ko/mod/mod_ssl.html
 [67]: http://httpd.apache.org/docs/2.2/ko/mod/mod_status.html
 [68]: http://httpd.apache.org/docs/2.2/ko/mod/mod_substitute.html
 [69]: http://httpd.apache.org/docs/2.2/ko/mod/mod_suexec.html
 [70]: http://httpd.apache.org/docs/2.2/ko/mod/mod_userdir.html
 [71]: http://httpd.apache.org/docs/2.2/ko/mod/mod_usertrack.html
 [72]: http://httpd.apache.org/docs/2.2/ko/mod/mod_vhost_alias.html