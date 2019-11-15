



拉取镜像

```
docker pull rabbitmq  #创建新容器
```

运行

```
docker run -d -p 5672:5672 --name myrabbit rabbitmq

```

进入容器

```vim
docker container exec -it myrabbit /bin/bash
```

新增用户,rabbitmqctl list_users获取用户列表

```
rabbitmqctl add_user username01 password01 2 # 这个用户名,密码在settings.py中使用
 
```

设置管理员

```
rabbitmqctl set_user_tags username01 administrator
```

添加虚拟环境,使用"rabbitmqctl list_vhosts"获取添加过的虚拟环境;

```
rabbitmqctl add_vhost myvhost # myvhost虚拟环境名称,同样在配置文件中需要使用
 
```

```vim
设置权限:给这个用户所有权限
rabbitmqctl set_permissions -p myvhost username01 ".*" ".*" ".*"
```

退出后重启

ctrl+d 退出容器且关闭

ctrl+p+q 退出容器但不关闭

```vim
docker restart myrabbit
```

配置完成

在settings.py中指定 消息队列的路径,和结果路径

2.5 版本以后

```python
BROKER_URL='amqp://hnq:123456@116.62.155.103:5672/myvhost'
CELERY_RESULT_BACKEND='amqp://hnq:123456@116.62.155.103:5672/myvhost'
 
```

格式:'amqp://用户名:密码@IP:端口号/虚拟环境'

在2.5 版本之前

```python
BROKER_HOST="116.62.155.103" #IP 2 BROKER_PORT=5672#端口号
BROKER_USER="hnq" #用户名
BROKER_PASSWORD="123456" #密码
BROKER_VHOST="/myvhost" #虚拟环境
```

```
redis-server ./redis.conf  #linux 启动redis
```



### 启动 阿里云上的redis

```vim
[root@iZbp1esh797fnbctu8kymhZ //]# find / -name redis
/usr/local/python3/lib/python3.7/site-packages/redis
/etc/selinux/targeted/tmp/modules/100/redis
/etc/selinux/targeted/active/modules/100/redis
^Z
[1]+  已停止               find / -name redis
[root@iZbp1esh797fnbctu8kymhZ //]# find / -name redis.conf
/home/soft/redis-4.0.2/redis.conf    在这个目录下用配置文件启动

# 查找redis客户端
find / -name redis-cli
find / -name redis.conf  查找redis配置文件
```

```
$ docker ps // 查看所有正在运行容器 
$ docker stop containerId // containerId 是容器的ID 
$ docker ps -a // 查看所有容器 $ docker ps -a -q // 查看所有容器ID 
$ docker stop $(docker ps -a -q) //  stop停止所有容器 
$ docker rm $(docker ps -a -q) //   remove删除所有容器  或docker rm 容器名
```

```
docker run -it --name redis-1 -v /root/redis.conf:/usr/local/etc/redis/redis.conf -d -p 6379:6379 redis /bin/bash
# 容器成功启动后，会打印一个长串的容器ID
```

