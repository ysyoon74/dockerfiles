# README

2022년6월21일 기준 CentOS의 오피셜 도커 이미지를 내려 받으면 yum repository 가 비정상적이기 때문에 repository를 변경한 버전을 생성

## 적용 방법
Official CentOS 이미지를 가져와 repository 를 변경한 후 commit 한다.

1. repository 변경하기
```
# 더미용 도커 컨테이너를 생성한다.
$ docker run -it --name centos centos
# 컨테이너 안에서 yum repository 정보를 변경한다.
[root@XXX]$ vi /etc/yum.repos.d/CentOS-Linux-AppStream.repo
...
# 기존 mirrolist 부분을 주석하고 아래 내용을 추가한다.
baseurl=http://vault.centos.org/$contentdir/$releasever/AppStream/$basearch/os/
...
# 저장 후 종료
[root@XXX]$ vi /etc/yum.repos.d/CentOS-Linux-BaseOS.repo
...
# 기존 mirrolist 부분을 주석하고 아래 내용을 추가한다.
baseurl=http://vault.centos.org/$contentdir/$releasever/BaseOS/$basearch/os/
...
# 저장 후 종료
```
2. docker commit 하기
```
$ docker commit <container_id> ysyoon74/centos:latest

```
