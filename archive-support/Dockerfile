From centos:7

MAINTAINER "yosefy" <yosef.yudilevich@gmail.com>


ENV GOROOT=/usr/local/go
#ENV GOPATH=/opt/go
ENV PATH=$PATH:$GOROOT/bin:$GOPATH/bin:/opt/libreoffice6.0/program
ENV GOVERSION=1.10.2
ENV OFFICE_VER=6.0.4

RUN yum -y update && yum -y upgrade && \
    yum -y install epel-release && \
    yum -y install wget git sudo bzip2 tmux gcc openssl cairo cups java-1.8.0-openjdk python-pip
    
RUN yum -y install https://download.postgresql.org/pub/repos/yum/9.6/redhat/rhel-7-x86_64/pgdg-centos96-9.6-3.noarch.rpm
RUN  yum -y install postgresql-client postgresql-contrib postgresql-devel
    
RUN pip install python-docx

WORKDIR /tmp
RUN curl https://dl.google.com/go/go$GOVERSION.linux-amd64.tar.gz | tar -xzf - -C /usr/local
RUN go version

RUN yum remove openoffice* libreoffice*
RUN curl -L https://download.documentfoundation.org/libreoffice/stable/${OFFICE_VER}/rpm/x86_64/LibreOffice_${OFFICE_VER}_Linux_x86-64_rpm.tar.gz | tar -xzf -

RUN cd LibreOffice_${OFFICE_VER}.2_Linux_x86-64_rpm/RPMS && yum install -y *.rpm && soffice --version
