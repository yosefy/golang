FROM golang

RUN apt-get update 
RUN apt-get install software-properties-common -y

RUN apt-add-repository ppa:libreoffice/ppa
RUN apt-get update
RUN apt-get install -y libreoffice --no-install-recommends
