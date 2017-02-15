---
title: life_cycle
date: 2017-02-15 17:46:22
tags: [php,zend extension]
categories: [php]
---

## 开始和结束

### PHP_MINIT_FUNCTION(myextension)/ZEND_MINIT_FUNCTION
- 第一阶段
- 模块初始化阶段；
- 注册模块常量，类等初始化操作；
- CLI和CGI模式（单进程模式）
```
PHP的生命周期在一次请求中完成。也就是说每次执行PHP脚本;
```
- 多进程模式：
```
多进程模式可以将PHP内置到Web Server中，
PHP可以编译成Apache下的prefork MPM模式和APXS模块，
当Apache启动后，会fork很多子进程，每个子进程拥有自己独立的进程地址空间；

在一个子进程中，PHP的生命周期是调用MINT启动后，执行多次请求（RINT/RSHUTDOWN)，
在Apache关闭或进程结束后，才会调用MSHUTDOWN进行回收阶段。

多进程模型中，每个子进程都是独立运行，没有代码和数据共享，
因此一个子进程终止退出和重新生成，不会影响其他子进程的稳定
```
- 多线程模式：
```
Apache2的Worker MPM采用了多线程模型，
在一个进程下创建多个线程，
在同一个进程地址空间执行,
一次M，多次R。
```
- FastCGI模式：
```
Fastcgi是一种特殊的CGI模式，是一种常驻进程类型的CGI，运行后可以Fork多个进程，
不用花费时间动态的Fork子进程，也不需要每次请求都调用MINT/MSHUTDOWN,
PHP通过PHP-FPM来管理和调度FastCGI的进程,
Nginx和PHP-FPM通过本地的TCP Socket和Unix Socket 进行通信。

Php-fpm启动时进程A会调用MINIT方法，
然后Fork出一个Fpm-Master进程B，(守护进程)，
然后进程B启动多个Php-CGI子进程C，
启动工作完成后，启动进程A就退出了（完成守护进程），
子进程在每个请求过来时调用RINIT。
```
- 嵌入式：
```
Embed SAPI是一种特殊的SAPI，允许在C/C++语言中调用PHP提供的函数;
这种SAPI和CLI模式一样，按照Module Init => Request Init => Request => Request Shutdown => Module Shutdown的模式运行
```

### PHP_RINIT_FUNCTION(myextension)/ZEND_RINIT_FUNCTION
- 第二阶段
- request上下文初始化

### PHP_RSHUTDOWN_FUNCTION(myextension)/ZEND_RSHUTDOWN_FUNCTION
- 第三阶段
- request上下文结束

### PHP_MSHUTDOWN_FUNCTION(myextension)/ZEND_MSHUTDOWN_FUNCTION
- 第四阶段
- 进程/线程结束