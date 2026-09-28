\# Ubuntu LAMP环境部署与故障排查项目

\## 项目介绍

在Ubuntu虚拟机搭建LAMP（Linux+Apache+MariaDB+PHP）网站运行环境，并且进行人为故障模拟、排查与修复练习。



\## 环境信息

\- 操作系统：Ubuntu

\- Apache版本：2.4.66

\- MariaDB版本：11.8.6

\- PHP版本：8.5.4



\## 一、部署步骤

1\. 安装Apache2网页服务

2\. 安装MariaDB数据库

3\. 安装PHP解析环境

4\. 安装phpMyAdmin数据库网页管理工具

5\. 数据库安全加固 mariadb-secure-installation

6\. 测试Apache静态页面

7\. 编写info.php测试PHP解析

8\. 创建软链接修复phpMyAdmin 404

9\. 登录phpMyAdmin验证数据库



\## 二、故障模拟实验

\### 故障1：停止Apache服务

\- 破坏操作：sudo systemctl stop apache2

\- 现象：浏览器访问IP无法打开网页

\- 原因：Apache Web服务停止，不再监听80端口，无法接收http请求

\- 修复命令：sudo systemctl start apache2

\- 验证：浏览器重新访问，页面恢复正常



\## 三、项目截图

!\[Apache It works页面](images/apache-itworks.png)

!\[PHP信息页面](images/php-info.png)

!\[phpMyAdmin后台页面](images/phpmyadmin-main.png)



\### 故障2：停止MariaDB数据库服务

\- 破坏操作：sudo systemctl stop mariadb

\- 现象：phpMyAdmin页面报错，无法连接数据库

\- 原因：MariaDB仓库服务停止，PHP无法连接数据库读取数据

\- 修复命令：sudo systemctl start mariadb

\- 验证：刷新phpMyAdmin页面，成功登录

