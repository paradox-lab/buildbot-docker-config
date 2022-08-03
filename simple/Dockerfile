FROM buildbot/buildbot-worker:master
USER root

RUN apt-get clean && \
    apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y --no-install-recommends \
    wget

RUN wget https://golang.google.cn/dl/go1.19.linux-amd64.tar.gz && \
    tar -C /usr/local -xzf go1.19.linux-amd64.tar.gz

ENV PATH $PATH:/usr/local/go/bin

RUN go env -w GOPROXY=https://goproxy.cn,direct
# 安装测试报告工具
RUN go install github.com/vakenbolt/go-test-report@latest