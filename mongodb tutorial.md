#MongoDB tutorial
###install an start up

1. 到官网下载MongoDB

2. 安装

3. 创建数据库文件的存放位置，比如d:/mongodb/data/db。启动mongodb服务之前需要必须创建数据库文件的存放文件夹，否则命令不会自动创建，而且不能启动成功。

4. 配置环境变量

5. 打开cmd，输入如下的命令启动mongodb服务（路径视个人情况而定）：  
>mongod dbpath d:mongodb/data/db

6. mongodb默认连接端口27017，如果出现如图的情况，可以打开http://localhost:27017查看（笔者这里是chrome），发现如图则表示连接成功，如果不成功，可以查看端口是否被占用。

7. 设为系统服务：在d:\mongodb\data下新建文件夹log（存放日志文件）并且新建文件mongodb.log，在d:\mongodb新建文件mongo.config。

8. 用记事本打开mongo.config输入：
>dbpath=D:\mongodb\data\db
logpath=D:\mongodb\data\log\mongo.log

9. 用管理员身份打开cmd命令行，输入如下的命令：
>mongod --config D:\mongodb\mongo.config --install --serviceName "MongoDB"

10. 打开cmd输入services.msc查看服务可以看到MongoDB服务，点击可以启动。