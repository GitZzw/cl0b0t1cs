## docker搭建golang容器
>> 参考study_go.md

### 1.创建go源文件

### 2. 创建golang镜像(使用 Dockerfile 定义应用程序的环境golang)
>> 在目录下创建Dockerfile，内容为

```
From golang
COPY . .
```

### 3.根据golang镜像创建容器
>> 在Dockerfile目录下创建

`docker build -t golang:test .`

### 4.进入golang容器
`docker run -it golang:test`

### 5.在命令行编译go文件
`cd hello`
` go build main.go`
`./main.go`
