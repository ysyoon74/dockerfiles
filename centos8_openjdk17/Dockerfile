FROM ysyoon74/centos:latest

LABEL maintainer="ysyun@saltlux.com"

USER root

RUN yum upgrade -y

RUN yum install -y \
	gcc \
	openssl-devel \
	bzip2-devel \
	libffi-devel \
	wget \
	make;

RUN dnf -y install java-17-openjdk