FROM centos:7

LABEL maintainer="ysyun@saltlux.com"

USER root

RUN yum install -y \
	java-1.8.0-openjdk \
	java-1.8.0-openjdk-devel

ENV JAVA_HOME /usr/lib/jvm/java-1.8.0-openjdk/

RUN export JAVA_HOME

RUN yum -y groupinstall 'Development Tools'

RUN yum install -y \
	gcc \
	openssl-devel \
	bzip2-devel \
	libffi-devel \
	wget;

RUN wget https://www.python.org/ftp/python/3.8.7/Python-3.8.7.tgz

RUN tar xvf Python-3.8.7.tgz

RUN rm Python-3.8.7.tgz

RUN cd Python-3.8.7 && \
	./configure --enable-optimizations && \
	make altinstall;

RUN cd .. && \
	rm -Rf Python-3.8.7

RUN ln -sf /usr/local/bin/python3.8 /usr/bin/python

RUN ln -s /usr/local/bin/pip3.8 /usr/bin/pip
