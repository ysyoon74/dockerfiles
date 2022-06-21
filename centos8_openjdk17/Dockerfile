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
	glibc-locale-source \
	make;

RUN localedef -f UTF-8 -i ko_KR ko_KR.utf8

ENV LANG=ko_KR.utf8 LANGUAGE=ko_KR:ko LC_ALL=ko_KR.utf8

RUN ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime

RUN dnf -y install java-17-openjdk