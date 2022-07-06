FROM golang:1.18-alpine
# RUN 设置代理镜像
RUN echo -e http://mirrors.ustc.edu.cn/alpine/v3.15/main/ > /etc/apk/repositories
# 镜像设置必要的环境变量
ENV GO111MODULE=on \
    CGO_ENABLED=0 \
    GOOS=linux \
    GOARCH=amd64 \
    GOPROXY="https://goproxy.cn,direct" \
    TZ=Asia/Shanghai

# 安装必要的软件包和依赖包
USER root
RUN apk --no-cache add git make bash ca-certificates tzdata curl vim

# 安装 goctl
USER root
RUN go install github.com/zeromicro/go-zero/tools/goctl@latest

# 安装 pprotoc & protoc-gen-go安装
USER root
RUN goctl env check -i -f --verbose

# 安装 modd
USER root
RUN go install github.com/cortesi/modd/cmd/modd@latest

# $GOPATH/bin添加到环境变量中
ENV PATH $GOPATH/bin:$PATH

# 设置工作目录
WORKDIR /code

CMD ["modd"]