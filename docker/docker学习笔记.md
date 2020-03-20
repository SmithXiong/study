### docker学习笔记
1. 安装virtualbox，修改虚拟机安装位置
2. 安装vagrant，将C:\Users\xm\.vagrant.d目录移动到指定磁盘，环境变量增加VAGRANT_HOME指向新路径E:\HashiCorp\.vagrant.d
3. 下载centos7的vagrant box，添加box命令
	```
	vagrant add box E:\downloads\CentOS-7-x86_64-Vagrant-1905_01.VirtualBox.box centos7
	vagrant box list //查看所有box
	```
4. 创建文件夹，初始化vagrantfile
	```
	mkdir centos7 //新建目录
	cd centos7 //切换目录
	vagrant init centos7 //初始化vagrant
	```
5. 修改vagrantfile,默认安装docker并启动
  ```
  config.vm.provision "shell", inline: <<-SHELL
    sudo yum install -y yum-utils device-mapper-persistent-data lvm2
    sudo yum-config-manager -y --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    sudo yum install -y docker-ce docker-ce-cli containerd.io
    sudo systemctl start docker
  SHELL
  ```
6. 启动虚拟机
	```
	vagrant up //安装并启动
	vagrant ssh //连接
	sudo su - //切换root用户
	docker version //查看docker版本
	exit //退出
	```
7. 当前用户提升docker权限
	```
	sudo groupadd docker //添加组
	sudo gpasswd -a vagrant docker //当前用户添加到组
	sudo service docker restart //重启docker
	exit //退出重新连接
	```
8. 多个虚拟机查看
	```
	vagrant global-status //查看所有虚拟机
	vagrant up [name|id] //启动
	vagrant halt [name|id] //关闭
	vagrant destroy [name|id] //删除
	```
9. docker container 命令
	```
	docker container ls -a //查看所有container
	docker ps -a
	docker container ls -aq //查看id
	docker container ls -a | awk {'pring$1'} //输出第一列
	docker container ls -f "status=exited" //列出退出状态的容器
	docker container rm $(docker container ls -aq) //删除所有容器
	docker rm [id|name]
	```
10. dockerfile 语法
	```
	FROM scratch //base image
	FROM centos
	FROM ubuntu:14.04
	LABEL maintainer="xxx@163.com" //作者
	LABEL version="1.0" //版本
	LABEL description="This is description" //描述
	RUN yum update && yum install -y vim \
		python-dev //运行命令反斜线换行
	WORKDIR /root //工作目录，没有会创建
	WORKDIR /test
	WORKDIR demo
	RUN pwd //输出/test/demo
	WORKDIR /root
	ADD hello test/  // /root/test/hello
	COPY hello test/
	ENV MYSQL_VERSION 5.6 //设置环境变量
	RUN apt-get install -y mysql-server= "${MYSQL_VERSION}" \ //引用常量
		&& rm -rf /var/lib/apt/lists/* //清除安装缓存
	```

