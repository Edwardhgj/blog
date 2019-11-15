---
title: 阿里云服务器如何安装mongodb？
abbrlink: d9ac2aad
date: 2019-06-28 21:01:40
---

1.下载mongodb

```
curl -O https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-3.2.9.tgz
```

2.解压

```
tar zxvf mongodb-linux-x86_64-3.2.9.tgz
```

3. 将解压过后的包移动到指定目录

```
mv mongodb-linux-x86_64-3.2.9/ /usr/local/mongodb
```

4.创建数据文件夹和日志文件等

```
mkdir -p  /usr/local/mongodb/data
touch /usr/local/mongodb/mongod.log
touch /usr/local/mongodb/mongodb.conf
```

5.启动方式（2种）

```
  cd /usr/local/mongodb/bin
```

（1）通过参数启动（通过mongodb客户端工具可直接访问）

```
./mongod --dbpath=/usr/local/mongodb/data --logpath=/usr/local/mongodb/mongod.log --logappend  --port=27017 --fork
```

(2)mongodb非法关闭的时候若出现 **about to fork child process, waiting until server is ready for connections** 那么需要执行

```
rm /data/mongodb/mongo.lock 命令
```

再执行

```
./mongod  --repair （命令修复）
```

(2) 通过配置文件启动 首先进行配置

```
vim /usr/local/mongodb/mongodb.conf 
```

```
dbpath=/usr/local/mongodb/data
logpath=/usr/local/mongodb/mongod.log
logappend = true 
port = 27017 
fork = true 
auth = true
```

加入后保存退出

```
:wq
```

进入mongo的bin目录下

```
cd /usr/local/mongodb/bin
```

再执行

```
./mongod --config /usr/local/mongodb/mongodb.conf
```

启动过程如果出现端口占用则使用 命令查看端口占用情况

```
ps aux | grep mongod
```



(停止)

```
./mongod -shutdown -dbpath=/usr/local/mongodb/data
```

6.配置安全组,开放端口  (27017,自定义TCP)

7.最后放开端口

/sbin/iptables -I INPUT -p tcp --dport 27017 -j ACCEPT







###  在阿里云ECS里用python连接mongodb官网提供的免费实例

2018.07.08 18:23:14字数 194阅读 304

上一篇我们已经能使用终端远程操作mongodb实例，这里我们使用python在自己的程序中来连接。

首先，根据官网提示，在python中我们使用以下代码可以连接：

client=pymongo.MongoClient("mongodb+srv://kay:myRealPassword@cluster0.mongodb.net/test")db=client.test

把其中的kay:myRealPassword改成自己设定的 用户名:密码即可

但是我写入后，运行python，提示：

The "dnspython" module must be installed to use mongodb+srv:// URIs

看来是少安装了一个包，于是果断

sudo pip install dnspython

再次运行即可进行连接。

对于不同语言，也有不同的连接命令，这个就等今后需要的时候再慢慢发掘了

https://blog.csdn.net/matthewwu/article/details/93733458







### 本地django连接阿里云mongo 增加数据

```python
#添加课程评论
import pymongo
class AddComment(APIView):
    def post(self, request):
        mes={}
        data = request.data.copy()
        print(data)
        try:
            pid=int(data['pid'])
        except:
            pid=0
        # 通过pic构造top_id，type_id
        if pid == 0:
            type_id = 1
            top_id = 0
        else:
            comment = models.Comment.objects.get(id=pid)
            type_id = comment.type_id + 1
            if comment.top_id==0:
                top_id = comment.id
            else:
                top_id = comment.top_id

        data['status'] = 1
        data['pid'] = pid
        data['top_id'] = top_id
        data['type_id'] = type_id
        data['reason'] = '请使用文明用语'
        data['comment_type'] = 'python'
        print(data)

        client = pymongo.MongoClient("47.96.238.24", 27017)  #建立连接
        db = client['onlineEducation']   # 创建库
        comm = db['comment']    # 创建集合
        comm.insert_one(data)    #插入数据

        mes['code'] = 200
        mes['message']='添加评论成功'

        return Response(mes)
```