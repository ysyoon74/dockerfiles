FROM ysyoon74/centos8_python39

LABEL maintainer="ysyun@saltlux.com"

USER root

RUN yum install -y \
	unzip \
	gcc-c++;

RUN python -m pip install -U \
	pip \
	setuptools \
	wheel \
	cmake;

RUN ln -sf /usr/local/bin/python3.9 /usr/bin/python3

RUN dnf install glibc-langpack-ko -y

RUN cd /opt && \
	wget https://github.com/kakao/khaiii/archive/refs/heads/master.zip && \
	unzip master.zip && \
	cd khaiii-master &&\
	mkdir build && \
	cd build && \
	cmake .. && \
	make all && \
	make large_resource && \
	make install && \
	make package_python && \
	cd package_python && \
	pip install .;
	
# 서비스를 위한 포트
EXPOSE 8080

# 컨테이너 실행시 명령어
ENTRYPOINT ["/bin/bash"]