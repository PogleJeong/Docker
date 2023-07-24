=======
Docker 에서 사용되는 Command
=======

# 1. docker build -t "image tag name" .

## 1. docker build
Dockerfile 을 사용하여 Docker Container Image 를 빌드함. Dockerfile 은 컨테이너 실행에 필요한 파일과 설정값을 포함하는 파일임

## 2. -t image 에 tag 지정
해당 Docker image 의 tag 를 "image tag name"으로 지정함.

## 3. 마지막 마침표 . 
지정한 폴더 내에 Dockerfile 을 봐야한다고 지정해줌.

# 2. docker run -dp 127.0.0.1:3300:3300 getting-started

## 1. docker run getting-started
getting-started docker image 실행

## 2. -d or --detach 
background 에서 container 실행

## 3. -p or --publish "host"
host 와 container 와 port mapping