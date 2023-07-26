commit command
======

docker hub 에서 필요한 image 를 pull 하고 run 하여 여러개의 container 를 만들고, 자신이 만들고 수정한 container 를 commit 명령어를 통해 새로운 image 를 생성할 수 있다.

# 0. 시나리오
ubtntu 환경에서 git 를 활용하여, php, python, nodejs 3가의 개발환경에 맞는 컨테이너 생성

# 1. image 를 통해 container 생성 및 container 환경설정

1. docker pull ubuntu
2. docker run -it ubuntu 

-it : container 생성하자마자 실행됨.
--name "my-container" : 컨테이너 이름지정.
bash : conatiner 안에서 bash 환경사용.

이후 cmd 에서 root@~~~~/# 이 나오면 성공

1. apt update : 최신상태로 갱신
2. apt install git : git 설치
3. git : git 실행

이쪽까지 한다면 my-ubuntu container 에만 설치가 된 것!


# 2. 새로운 image 생성

지금까지 만든 my-ubuntu container 를 commit 하여 image 생성

1. #exit 

2. docker commit my-ubuntu egoing:ubuntu-git : my-ubuntu container 를 이용하여 이름이 egoing 이고 tag가 ubuntu-git 인 image 생성

3. docker images 
image 생성 확인

# 3. git 환경의 image 를 가지고 3개의 container 생성


## 1, nodejs
- docker run -it --name nodejs egoing:ubuntu-git bash
- apt update && apt install nodejs

## 2. python
- docker run -it --name python egoing:ubuntu-git bash
- apt update && apt install python3



나중에 더 체계적이고 명시적이게 image 와 container 를 구성하기 위해서는 Dockerfile 과 docker build 명령어를 사용한다!