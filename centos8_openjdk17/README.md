# 적용 가이드

## 전제 조건
  - 2022년6월21일 기준 CentOS의 오피셜 도커 이미지를 내려 받으면 yum repository 가 비정상적이기 때문에 ysyoon74/centos 를 받아서 사용한다.

## Docker image 만들기
  1. 터미널에서 아래와 같이 실행한다.
  ```
  # Dockerfile 이 있는 곳으로 이동
  $ cd centos8_openjdk17
  # 이미지 빌드하기
  $ docker build -t centos8_openjdk17:latest .
  # 이미지 확인하기
  $ docker images
  REPOSITORY                             TAG                   IMAGE ID       CREATED             SIZE
  ysyoon74/centos8_openjdk17             latest                d0af1e44df21   About an hour ago   995MB
  ```
  2. 추가 설정하기
  ```
  # 더미용 도커 컨테이너 만들기
  $ docker run -i --privileged ysyoon74/centos8_openjdk17
  # 컨테이너 안에서 아래 설정
  [root@XXX]$ sysctl -w vm.max_map_count=262144
  # 다른 터미널을 이용해 도커 이미지에 commit 하기
  $ docker commit <container_id> ysyoon74/centos8_openjdk17:latest
  ```
