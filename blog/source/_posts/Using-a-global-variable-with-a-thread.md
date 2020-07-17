---
title: signal handler in linux using C
date: 2020-07-16 15:04:43
tags:
---

讀取linux signal的簡單範例

## signal.c


``` two thread example
#include <stdio.h>	 //file and standard io
#include <stdlib.h>	//exit
#include <signal.h>	//sigaction


//catch signal and do exit(0) 
void signal_handler(int signum)
{
	printf("Get signal: %d\n",signum);
	system("killall Wialon_demo");
	exit(0);
}
//catch registered signal and call signal_handler
//SIGINT  2			Ctrl-C	
//SIGQUIT 3			Ctrl-\
//SIGTERM 15		killall
void init_signal()
{
	struct sigaction sa_usr;
	sa_usr.sa_flags = 0;
	sa_usr.sa_handler = signal_handler;		
	sigaction(SIGINT,&sa_usr,NULL);
	sigaction(SIGTSTP,&sa_usr,NULL);
	sigaction(SIGQUIT,&sa_usr,NULL);
	sigaction(SIGTERM,&sa_usr,NULL);
}
int main()
{
	
	init_signal();

	while(1)
	{
		;
	}
	return 0;
}
``` 






