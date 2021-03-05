# docker

### docker基于linux内核 先要安装linux (hyper-V)

### systeminfo   x64 arm64 指令集差别

### 安装教程
>> https://www.runoob.com/docker/windows-docker-install.html
>> https://docs.microsoft.com/zh-cn/windows/wsl/install-win10

### docker基本概念
>> 镜像 容器...

### docker使用
`docker run ubuntu:15.10 /bin/echo "Hello world"  `
>> Docker 以 ubuntu15.10 镜像创建一个新容器，然后在容器里执行 bin/echo "Hello world"，然后输出结果。  Docker 首先从本地主机上查找镜像是否存在，如果不存在，Docker 就会从镜像仓库 Docker Hub 下载公共镜像

`docker run -i -t ubuntu:15.10 /bin/bash`
>> 运行交互式的容器  exit 退出

`docker run -d ubuntu:15.10 /bin/sh -c "while true;do echo hello world;sleep 1;done"`
>> 创建一个以进程方式运行的容器
>> docker ps 查看容器在运行
>> docker logs ID(Name) 查看对应容器输出信息
>> docker stop 停止容器

`docker exec -it 243c32535da7 /bin/bash`
>> 进入容器

`docker export 1e560fca3906 > ubuntu.tar`
>> 导出容器快照到本地ubuntu.tar

`cat docker/ubuntu.tar | docker import - test/ubuntu:v1`
`docker import http://example.com/exampleimage.tgz example/imagerepo`
>> docker import 从容器快照文件中再导入为镜像


### 运行一个 web 应用
`docker pull training/webapp`  # 载入镜像
`docker run -d -p 5000:5000 training/webapp python app.py`
>> 参数说明 -d:让容器在后台运行。  -P:将容器内部使用的网络端口随机映射到我们使用的主机上。 -p : 是容器内部端口绑定到指定的主机端口。
>> 浏览器访问 http://localhost:5000/


### docker镜像使用
>> https://www.runoob.com/docker/docker-image-usage.html

`docker pull ubuntu:13.10`  
`docker search httpd`
>> 查找镜像 https://hub.docker.com/

## docker容器链接
>> https://www.runoob.com/docker/docker-container-connection.html

`docker run -d -p 127.0.0.1:5001:5000 training/webapp python app.py`
>> 指定容器绑定的网络地址，比如绑定 127.0.0.1

`docker run -d -P --name runoob training/webapp python app.py`
>> 容器命名

`docker network create -d bridge test-net`
>> 创建新的docker网络

`docker run -itd --name test1 --network test-net ubuntu /bin/bash`
>> 运行一个容器并连接到新建的 test-net 网络

`docker run -itd --name test2 --network test-net ubuntu /bin/bash`
>> 打开新的终端，再运行一个容器并加入到 test-net 网络


### docker 镜像构建上下文理解
<< https://www.cnblogs.com/lfxiao/p/9594185.htmls
