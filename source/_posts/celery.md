---
title: 练习用原生JavaScript编写与JavaScript数组方法slice功能一样的函数
abbrlink: d9ac2aad
date: 2017-06-28 21:01:40
---


<html>

<div class="mark_content art_article">
                            <p>鉴于公司项目及业务发展，技术人员从几人到如今几十人，后端团队技术人员日益剧增，可是随着项目人员的增长，大多研发人员及相关人员经常需要到测试环境使用 MySQL 数据库，比如移动端、测试、产品，然而他们需要普及 MySQL 知识点及性能优化的知识，其实性能优化的目标是针对后端研发人员及一些资深的前端人员，可能会从如下大的知识点讲解。</p>
<h3>一、安装说明</h3>
<p>首先学习数据库，当然是安装软件。千里之行，始于足下，如果连安装都不会，如何进行后续的入门学习。可是对于安装也有不同方式，比如 RPM 和源码编译安装呢。</p>
<h4>1.1 RPM 安装包和 Tar 安装包的区别？</h4>
<p>RPM 直接安装，Tar 属于源码安装，可以设置更多的参数，可以和系统进行更紧密的优化。举个例子，RPM 是 180/96、185/100 之类的标准版型，Tar 源码安装类似于私人定制，量体裁衣的。其实个人觉得 RPM 安装适合小白入门，简单了解下 MySQL，不用做过多安装上的了解，然而源码编译安装适合比如经常跟 MySQL 打交道的工程师，比如 web 研发人员、c++ 工程师等，总不能只是知道如何简单的使用和 curd，其实对于技术人员的纵向知识体系打造是不好的，其实源码编译安装，还可能自己尝试些具体参数的配置。关于 MySQL 官方下载地址：</p>
<blockquote>
  <p><a href="https://dev.mysql.com/downloads/mysql/?utm_source=so&amp;utm_source=so">https://dev.mysql.com/downloads/mysql/</a></p>
</blockquote>
<h4>1.2 安装后需要配置哪些内容？</h4>
<p>不管 RPM 还是源码编译安装后，有些东西必须要设置：</p>
<ul>
<li><p>root 初始密码问题：必须设置密码，如果是自己玩还好，如果是线上系统必须设置密码，要不然就是裸跑系统。</p></li>
<li><p>默认安装后会在指定文件中生成，如果忘记或找不到可以对 root 密码进行强制修改：</p>
<p>mysqld_safe –skip-grant-tables 2&amp; </p></li>
<li><p>用户远程访问问题：从安全性角度默认不允许远程访问，可以进行配置，允许远程访问，但是要注意安全性规范。</p>
<p>grant all privileges on . to ‘root’@’%’ identified by’Password’; 
flush privileges;</p></li>
<li><p>UTF-8 编码问题： 关于字符集的问题，可能有些技术人员初次学习数据库时或者初次从事研发工作时，偶尔会碰到，为什么前端信息是正常录入，写入数据库时，变成了乱码？查看数据库的编码方式命令为：</p>
<p>show variables like 'character%';</p>
<p>参数说明：
character<em>set</em>client为客户端编码方式；
character<em>set</em>connection为建立连接使用的编码；
character<em>set</em>database数据库的编码；
character<em>set</em>results结果集的编码；
character<em>set</em>server数据库务器的编码；</p></li>
</ul>
<h4>1.3 my.cnf 文件初始需要配置哪些内容？</h4>
<ul>
<li><p>数据文件位置： 确保数据不会把磁盘空间写满，如果有 ssd，可以充分利用 IO 优势。</p></li>
<li><p>日志文件位置： 快速定位错误日志的位置，根据日志排除错误的能力，是程序员的第一生产力。</p></li>
<li><p>其他基础参数</p></li>
<li><p>Myisam系列参数（表级锁）：事务--锁--？</p>
<p>myisam<em>sort</em>buffer<em>size = 128M   
myisam</em>max<em>sort</em>file<em>size = 10G   
myisam</em>max<em>extra</em>sort<em>file</em>size = 10G
myisam<em>repair</em>threads = 1<br>
myisam_recover   </p></li>
<li><p>InnoDB系统参数（行级锁？）：</p>
<p>innodb<em>additional</em>mem<em>pool</em>size = 16M<br>
innodb<em>buffer</em>pool<em>size = 2048M   
innodb</em>data<em>file</em>path = ibdata1:1024M:autoextend<br>
innodb<em>file</em>io<em>threads = 4   
innodb</em>thread<em>concurrency = 8   
innodb</em>flush<em>log</em>at<em>trx</em>commit = 2<br>
innodb<em>log</em>buffer<em>size = 16M  
innodb</em>log<em>file</em>size = 128M<br>
innodb<em>log</em>files<em>in</em>group = 3<br>
innodb<em>max</em>dirty<em>pages</em>pct = 90<br>
innodb<em>lock</em>wait<em>timeout = 120   
innodb</em>file<em>per</em>table = 0 </p></li>
<li><p>其他参数</p>
<p>[client]
port = 3306
socket =
                        </p></li></ul></div>
</html>