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
RUN curl https://dl.google.com/go/go$GOVERSION.linux-amd64.tar.gz | tar -xzf - -C /usr/local
RUN go version

RUN yum remove openoffice* libreoffice*
RUN wget http://download.documentfoundation.org/libreoffice/stable/6.0.0/rpm/x86_64/LibreOffice_6.0.0_Linux_x86-64_rpm.tar.gz

RUN tar -xvf LibreOffice_6.0.0_Linux_x86-64_rpm.tar.gz
RUN cd /tmp/LibreOffice_6.0.0.3_Linux_x86_rpm/RPMS/ && yum localinstall *.rpm
