---
layout: post
title: 简说僵尸进程、守护进程与托管进程
author: nathena
tags:  [linux,c,c++]
categories: [linux_c_cpp]
---

## 托管进程

> 因为父进程异常结束了，然后被1号进程init收养


## 僵尸进程

> 一个进程使用fork创建子进程，如果子进程退出，父进程还在运行且父进程并没有调用wait或waitpid获取子进程的状态信息，那么子进程的进程描述符仍然保存在系统中。这种进程称之为僵死进程


## 守护进程

> 创建守护进程时有意把父进程结束，然后被1号进程init收养


```

一个正常运行的子进程，如果此刻子进程退出，正在运行中的父进程没有及时调用wait或waitpid收回子进程的系统资源，该进程就是僵尸进程，如果系统收回了，就是正常退出，如果一个正常运行的子进程，父进程退出了但是子进程还在，该进程此刻是托管进程，被init收养，如果父进程是故意被杀掉，子进程做相应处理后就是守护进程

```

## 那么

为了保证守护进程能正常创建，而不收启动进程的影响我们要这么干。父进程先fork出一个儿子进程，儿子进程再fork出孙子进程做为守护进程，然后儿子进程立刻退出，守护进程被init进程接管，这样无论父进程做什么事，无论怎么被阻塞，都与守护进程无关了。所以，fork两次的守护进程很安全，避免了僵尸进程出现的可能性。


```

#include <stdio.h>
#include <unistd.h>
#include <sys/wait.h> 

void _deamon(void)
{
	pid_t pid;

	if( ( pid = fork() )>0 )
	{
		printf("Parent is printing \n");
		exit(1);
	}
	else if( pid < 0 )
	{
		printf("Parent fork failed %d\n", pid );
		exit(1);
	}

	printf("Frist Child is printing\n");

	setsid();

	if( ( pid = fork() )>0 )
	{
		printf("Second Parent is printing \n");
		exit(1);
	}
	else if( pid < 0 )
	{
		printf("Second Parent fork failed %d\n", pid );
		exit(1);
	}

	printf("Second Child is printing\n");
	
}

int main(int argc, char const *argv[])
{
   
   _deamon();
   
   return 0;
}


``` 