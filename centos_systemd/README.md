# 실행하기
```
docker run --privileged --name centos_demo -p 80:80 -itd -e container=docker -v /sys/fs/cgroup:/sys/fs/cgroup centos7-systemd /usr/sbin/init
```
