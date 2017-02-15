---
layout: post
title: c标准库
author: nathena
tags:  [linux,c,c++]
categories: [linux_c_cpp]
date: 2016-04-05
---



```

> #include <assert.h> 
标准库的头文件中提供了一个宏称为断言可以用于验证程序的假设，如果这个假设是错误的，并打印诊断消息。


> #include <ctype.h> //字符处理
提供的声明几个有用的函数测试和字符映射。所有的功能都接受int作为参数，其值必须是EOF或为unsigned char表示。所有函数返回的参数c非零（true），如果满足条件。否则返回0。


#include <errno.h> //定义错误码
#include <float.h> //浮点数处理
#include <limits.h> //定义各种数据类型最值常量
#include <locale.h> //定义本地化函数
#include <math.h> //定义数学函数
#include <setjmp.h> //文件输入／输出

> #include <signal.h> 
signal.h头文件中定义变量类型sig_atomic_t，两个函数调用和几个宏处理程序的执行过程中不同的信号报告。

> #include <stdarg.h> 
不定参数

#include <stdio.h> //定义输入／输出函数
#include <stdlib.h> //定义杂项函数及内存分配函数
#include <string.h> //字符串处理

#include <time.h> //定义关于时间的函数

> #include <stddef.h> 
stddef.h 头文件定义了各种变量的类型和宏。许多这些定义也出现在其他头。


1.Linux中一些头文件的作用：
#include <assert.h>       //ANSI C。提供断言，assert(表达式) 
#include <glib.h>           //GCC。GTK，GNOME的基础库，提供很多有用的函数，如有数据结构操作函数 
#include <dirent.h>        //GCC。文件夹操作函数 
#include <ctype.h>        //ANSI C。字符测试函数。isdigit(),islower()等 
#include <errno.h>        //ANSI C。查看错误代码errno是调试程序的一个重要方法 
#include <getopt.h>     //处理命令行参数 

2.linux常用头文件如下：
//POSIX标准定义的头文件 
#include <dirent.h>        //目录项 
#include <fcntl.h>         //文件控制 
#include <fnmatch.h>       //文件名匹配类型 
#include <glob.h>          //路径名模式匹配类型 
#include <grp.h>           //组文件 
#include <netdb.h>         //网络数据库操作 
#include <pwd.h>           //口令文件 
#include <regex.h>           //正则表达式 
#include <tar.h>           //TAR归档值 
#include <termios.h>       //终端I/O 
#include <unistd.h>        //符号常量 
#include <utime.h>         //文件时间 
#include <wordexp.h>       //字符扩展类型 
//————————- 
#include <arpa/inet.h>     //INTERNET定义 
#include <net/if.h>        //套接字本地接口 
#include <netinet/in.h>    //INTERNET地址族 
#include <netinet/tcp.h>   //传输控制协议定义 
//————————- 
#include <sys/mman.h>      //内存管理声明 
#include <sys/select.h>    //Select函数 
#include <sys/socket.h>    //套接字借口 
#include <sys/stat.h>      //文件状态 
#include <sys/times.h>     //进程时间 
#include <sys/types.h>     //基本系统数据类型 
#include <sys/un.h>        //UNIX域套接字定义 
#include <sys/utsname.h>   //系统名 
#include <sys/wait.h>      //进程控制 
//—————————— 
//POSIX定义的XSI扩展头文件 
#include <cpio.h>          //cpio归档值 
#include <dlfcn.h>         //动态链接 
#include <fmtmsg.h>        //消息显示结构 
#include <ftw.h>           //文件树漫游 
#include <iconv.h>         //代码集转换使用程序 
#include <langinfo.h>      //语言信息常量 
#include <libgen.h>        //模式匹配函数定义 
#include <monetary.h>      //货币类型 
#include <ndbm.h>          //数据库操作 
#include <nl_types.h>      //消息类别 
#include <poll.h>          //轮询函数 
#include <search.h>        //搜索表 
#include <strings.h>       //字符串操作 
#include <syslog.h>        //系统出错日志记录 
#include <ucontext.h>      //用户上下文 
#include <ulimit.h>        //用户限制 
#include <utmpx.h>         //用户帐户数据库 
//—————————– 
#include <sys/ipc.h>       //IPC(命名管道) 
#include <sys/msg.h>       //消息队列 
#include <sys/resource.h>  //资源操作 
#include <sys/sem.h>       //信号量 
#include <sys/shm.h>       //共享存储 
#include <sys/statvfs.h>   //文件系统信息 
#include <sys/time.h>      //时间类型 
#include <sys/timeb.h>     //附加的日期和时间定义 
#include <sys/uio.h>       //矢量I/O操作 
//—————————— 
//POSIX定义的可选头文件 
#include <aio.h>           //异步I/O 
#include <mqueue.h>        //消息队列 
#include <pthread.h>       //线程 
#include <sched.h>         //执行调度 
#include <semaphore.h>     //信号量 
#include <spawn.h>         //实时spawn接口 
#include <stropts.h>       //XSI STREAMS接口 
#include <trace.h>         //事件跟踪 

3.C/C++头文件一览：
//C 
#include <assert.h>　　　　//设定插入点 
#include <ctype.h>　　　　 //字符处理 
#include <errno.h>　　　　 //定义错误码 
#include <float.h>　　　　 //浮点数处理 
#include <iso646.h>        //对应各种运算符的宏 
#include <limits.h>　　　　//定义各种数据类型最值的常量 
#include <locale.h>　　　　//定义本地化C函数 
#include <math.h>　　　　　//定义数学函数 
#include <setjmp.h>        //异常处理支持 
#include <signal.h>        //信号机制支持 
#include <stdarg.h>        //不定参数列表支持 
#include <stddef.h>        //常用常量 
#include <stdio.h>　　　　 //定义输入／输出函数 
#include <stdlib.h>　　　　//定义杂项函数及内存分配函数 
#include <string.h>　　　　//字符串处理 
#include <time.h>　　　　　//定义关于时间的函数 
#include <wchar.h>　　　　 //宽字符处理及输入／输出 
#include <wctype.h>　　　　//宽字符分类 
 
//传统C++ 
#include <fstream.h>　　　 //改用<fstream> 
#include <iomanip.h>　　　 //改用<iomainip> 
#include <iostream.h>　　　//改用<iostream> 
#include <strstrea.h>　　　//该类不再支持，改用<sstream>中的stringstream 
//———————————————————————————————— 
 
//标准C++ 
#include <algorithm>　　　 //STL 通用算法 
#include <bitset>　　　　　//STL 位集容器 
#include <cctype>          //字符处理 
#include <cerrno> 　　　　 //定义错误码 
#include <cfloat>　　　　 //浮点数处理 
#include <ciso646>         //对应各种运算符的宏 
#include <climits> 　　　　//定义各种数据类型最值的常量 
#include <clocale> 　　　　//定义本地化函数 
#include <cmath> 　　　　　//定义数学函数 
#include <complex>　　　　 //复数类 
#include <csignal>         //信号机制支持 
#include <csetjmp>         //异常处理支持 
#include <cstdarg>         //不定参数列表支持 
#include <cstddef>         //常用常量 
#include <cstdio> 　　　　 //定义输入／输出函数 
#include <cstdlib> 　　　　//定义杂项函数及内存分配函数 
#include <cstring> 　　　　//字符串处理 
#include <ctime> 　　　　　//定义关于时间的函数 
#include <cwchar> 　　　　 //宽字符处理及输入／输出 
#include <cwctype> 　　　　//宽字符分类 
#include <deque>　　　　　 //STL 双端队列容器 
#include <exception>　　　 //异常处理类 
#include <fstream> 　　　  //文件输入／输出 
#include <functional>　　　//STL 定义运算函数（代替运算符） 
#include <limits> 　　　　 //定义各种数据类型最值常量 
#include <list>　　　　　　//STL 线性列表容器 
#include <locale>          //本地化特定信息 
#include <map>　　　　　　 //STL 映射容器 
#include <memory>          //STL通过分配器进行的内存分配 
#include <new>             //动态内存分配 
#include <numeric>         //STL常用的数字操作 
#include <iomanip> 　　　  //参数化输入／输出 
#include <ios>　　　　　　 //基本输入／输出支持 
#include <iosfwd>　　　　　//输入／输出系统使用的前置声明 
#include <iostream> 　　 　//数据流输入／输出 
#include <istream>　　　　 //基本输入流 
#include <iterator>        //STL迭代器 
#include <ostream>　　　　 //基本输出流 
#include <queue>　　　　　 //STL 队列容器 
#include <set>　　　　　　 //STL 集合容器 
#include <sstream>　　　　 //基于字符串的流 
#include <stack>　　　　　 //STL 堆栈容器 
#include <stdexcept>　　　 //标准异常类 
#include <streambuf>　　　 //底层输入／输出支持 
#include <string>　　　　　//字符串类 
#include <typeinfo>        //运行期间类型信息 
#include <utility>　　　　 //STL 通用模板类 
#include <valarray>        //对包含值的数组的操作 
#include <vector>　　　　　//STL 动态数组容器 
//———————————————————————————————— 
 
//C99增加的部分 
#include <complex.h>　　 //复数处理 
#include <fenv.h>　　　　//浮点环境 
#include <inttypes.h>　　//整数格式转换 
#include <stdbool.h>　　 //布尔环境 
#include <stdint.h>　　　//整型环境 
#include <tgmath.h>　　　//通用类型数学宏


```