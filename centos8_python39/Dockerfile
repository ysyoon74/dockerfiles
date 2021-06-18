FROM centos

LABEL maintainer="ysyun@saltlux.com"

USER root

RUN yum install -y \
	gcc \
	openssl-devel \
	bzip2-devel \
	libffi-devel \
	xz-devel \
	wget \
	sqlite-devel \
	make;

RUN wget https://www.python.org/ftp/python/3.9.5/Python-3.9.5.tgz

RUN tar xvf Python-3.9.5.tgz

RUN rm Python-3.9.5.tgz

RUN cd Python-3.9.5 && \
	./configure --enable-optimizations && \
	make altinstall;

RUN ln -sf /usr/local/bin/python3.9 /usr/bin/python

RUN ln -s /usr/local/bin/pip3.9 /usr/bin/pip
