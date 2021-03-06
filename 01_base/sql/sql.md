### 1. 数据的存储方式  
```
文件,内存.第三方服务器,数据库服务器
``` 
### 2. 数据库的发展历史 
``` 
网状数据库,层次型数据库,
关系型数据库,非关系型数据库(NoSQL)
```
### 3. 关系型数据库
```
数据库中也是按照一定的顺序存放数据, 目的是为了操作数据——增删改查
关系型数据库的逻辑结构
Server  ->  Database  -> Table  ->  Row  ->  Column
```
### 4. 使用MySQL
```sql
# Oracle: mysql
# Martin: MariaDB

# XAMPP
是一个服务器套装，包括多款服务器软件
https://www.apachefriends.org/zh_cn/download.html
#(1)部署结构
  服务器端：负责存储/维护数据 ——— 银行的数据库服务器
    C:/xampp/mysql/bin/mysqld.exe 
  确保端口3306不被占用
  客户端：负责连接数据库，执行增删改查 —— ATM机
    C:/xampp/mysql/bin/mysql.exe
#(2)连接数据库
  mysql.exe   -h127.0.0.1   -P3306   -uroot   -p
  -h   host（主机：IP地址/域名）  127.0.0.1/localhost   指向当前自己的电脑
  -P   Port（端口）   默认使用3306
  -u   user（用户名）   root 用户是管理员
  -p   password（密码）  xampp下root用户的密码为空
  mysql -uroot 简写形式
  连接命令后不能加分号，加分号用户名为(root;)，变成了游客身份。
#(3)mysql常用管理命令
  quit;    退出服务器的连接
  show  databases;   显示当前服务器下所有的数据库
  use  数据库名称;   进入指定的数据库
  show  tables;   显示当前数据库中所有的表
  desc  表名称;   描述表中都有哪些列
  所有的命令都要以英文的分号结尾
```
### 5. SQL语句的执行方式
```bash
#(1)交互模式
  客户端输入一行回车，服务器端执行一行；适用于临时性查看数据
#(2)脚本模式
  客户端把要执行的命令写在一个脚本文件中，然后一次性的提交给服务器执行；适用于批量的操作数据
  #在建立连接前执行以下命令
  # mysql  -uroot<拖拽脚本文件到此位置     回车
(3)SQL的语法规范
  一行SQL语句可以跨越多行，以英文的分号作为结尾
  SQL语句中习惯上关键字大写，非关键字小写
  假设某一条SQL语句出现错误，则此条语句往后所有的语句不再执行
  分为单行注释(#...)和多行注释(/*...*/)，注释的内容不会被服务器所执行
```
### 6. 计算机如何存储字符
```bash
(1)如何存储英文字符
  ASCII  对所有的英文字母及其符号进行了编码，总共有128个
  Latin-1   对所有的欧洲字符进行了编码，兼容ASCII，总共有256个
(2)如何存储中文字符
  GB2312  对常用的6千多汉字进行了编码，兼容ASCII
  GBK   对2万多的汉字进行了编码，兼容GB2312
  BIG5   台湾繁体字编码
  Unicode   对世界上主流国家的常用语言进行了编码，兼容ASCII，具体三种存储方案UTF-8,UTF-16,UTF-32
(3)mysql中文乱码
  mysql默认使用Latin-1，不兼容中文，因此出现乱码
#(4)解决mysql中文乱码
  脚本文件另存为的编码为UTF8
  客户端连接服务器端的编码为UTF8
  SET  NAMES  UTF8;
  服务器端创建数据库使用的编码为UTF8
  CREATE  DATABASE  xz  CHARSET=UTF8;
```







