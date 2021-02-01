---
title: ngrinder 에이전트 데몬으로 돌리기..
author: netggio
layout: post
permalink: /archives/2253
categories:
  - 일~일~일/Script 모음
tags:
  - daemon
  - ngrinder
  - ngrinder agent daemon
---
ngrinder이 보니.. 백그라운드 형식으로 밖에 돌리지를 못하는 형식으로 제공이 된다..

&붙여서 돌리면 되긴 하지만 살짝 아쉬운 경우라.. screen을 이용해서 아래와 같이 데몬 행태로 돌릴수 있다..

screen는 설치가 되어 있어야 한다..

<pre class="brush:bash">#!/bin/bash
#
# ngrinder_agent         Start up the ngrinder_agent daemon
#
# processname: ngrinder_agent
### BEGIN INIT INFO
# Default-Start: 2 3 4 5
# Default-Stop: 0 1 6
#                    This service starts up the ngrinder_agent server daemon.
### END INIT INFO


DAEMON="ngrinder_agent"
IDENT="ngrinder_agent"
PREFIX="/home/ngrinder-core-3.2.3"
RUNFILE="/var/run/ngrinder_agent.run"


start() {
        [ -e ${RUNFILE} ] && stop
        touch $RUNFILE
        echo -n "starting $DAEMON"
        screen -d -m -S ${IDENT} ${PREFIX}/run_agent.sh &
        echo -n "."
        echo ""
}

stop() {
        echo "stopping $DAEMON"
        screen -list | grep \.${IDENT} | cut -d\. -f1 | xargs -r kill -9
        screen -wipe > /dev/null 2>&1
        rm -f ${RUNFILE} 2>/dev/null
}

case "$1" in
        start)  start
                ;;
        stop)   stop
                ;;
        status)
          chk=`screen -list | grep \.${IDENT} | awk '{print $1}' | wc -l`
          ppid=`screen -list | grep ngrinder_agent | awk '{print $0}' | awk -F\. '{print $1}'| xargs`
                if [ $chk == 1 ]
                        then
                          echo "$DAEMON is (pid $ppid) running.."
                         exit 0
                        else
                          echo "$DAEMON is not running.."
                         exit 1
                fi
                ;;
        restart)stop
                start
                ;;
        *)      echo -n "usage:\n\t$0 (start|stop|status|restart)\n"
                exit 1
                ;;
esac
exit 0

</pre>