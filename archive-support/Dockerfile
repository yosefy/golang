From centos:7

MAINTAINER "UshioShugo" <ushio.s@gmail.com>


ENV GOROOT=/usr/local/go
ENV GOPATH=/opt/go
ENV PATH=$PATH:$GOROOT/bin:$GOPATH/bin
#ENV GOVERSION=$GO_VER
ENV GOVERSION=1.10.2


RUN yum -y update && yum -y upgrade && \
    yum -y install epel-release && \
    yum -y install wget git sudo bzip2 tmux gcc openssl

WORKDIR /tmp
RUN curl https://dl.google.com/go/go$GOVERSION.linux-amd64.tar.gz | tar -C /usr/local -xzf go$GOVERSION.linux-amd64.tar.gz
RUN go version
