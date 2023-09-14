# sillygirl
docker傻妞旧版本教程

#拉库命令：

docker run -itd --name sillygirl -p 8080:8080 --restart always -v "$(pwd)"/sillyGirl:/etc/sillyGirl ingm23/sillygirl:1.1

然后打开https://github.com/ingm23/sillygirl 下载替换文件

把sillygirl.cache 替换服务器sillyGirl路径下的同名文件

然后重启傻妞 docker restart sillygirl 

完成之后打开网页  ip:8080  输入账号：傻妞 密码：123456   就可以登录

服务器傻妞交互模式代码命令  docker attach sillygirl 

设置密码命令  set silly password  密码



#高级命令


创建该容器的快照。可以使用 docker commit 命令来创建快照，该命令会生成一个作为Docker镜像的容器快照

例子 ： docker commit -p 30b8f18f20b4 container-backup




#传输文件到docker容器

首先需要知道docker容器的container_id,可以使用docker ps命令来查看你要操作的docker容器的container_id

1.Docker容器向宿主机传送文件：

格式：

　　docker cp container_id:<docker容器内的路径> <本地保存文件的路径>

例子：

　　docker cp a185c175d756:/root/test.txt /Users/luochao7/Documents

 

2.宿主机向Docker容器传送文件：

格式：

　　docker cp 本地文件的路径 container_id:<docker容器内的路径>

例子：

　　docker cp /Users/luochao7/Downloads/jdk-8u191-linux-x64.tar.gz a185c175d756:/root/
