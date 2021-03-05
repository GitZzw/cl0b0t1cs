## docker搭建golang容器
>> 参考study_go.md

### 1.创建go源文件

### 2. 创建golang镜像(使用 Dockerfile 定义应用程序的环境golang)
>> 在目录下创建Dockerfile，内容为

```
From golang
MAINTAINER "ZZW"
RUN go env -w GO111MODULE=on && go env -w GOPROXY=https://goproxy.cn,direct && go get -u gorm.io/gorm && go get -u gorm.io/driver/sqlite
COPY . .
RUN cd src/hello && go mod init hello && go mod tidy && go build main.go
```

### 3.创建golang镜像
>> 在Dockerfile目录下创建

`docker build -t golang:test .`

### 4.根据镜像创建容器 进入交互式界面
`docker run -it golang:test`

### 5.在命令行编译go文件
`./main.go`
