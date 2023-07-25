=======
Docker Install on Windows
=======

# 0. Docker Desktop 설치 및 싱행

[설치페이지] (https://docs.docker.com/desktop/install/windows-install/)

Docker Desktop 실행
- 임직원 250인 미만, 연매출 1000만달러 미만 중소사업자나, 개인, 교육, 비상업적 사용은 무료
- 전문적인 사용을 원한다면 유료구독 필요, 정부기관 또한 유료구독.
- Docker Pro, Team 및 Business 를 구독하는 것은 상업적사용으로 봄

# 1. Containerize an application

[컨테이너화] (https://docs.docker.com/get-started/02_our_app/)

## 1. docker 에서 제공하는 text app 을 clone (테스트)

>$git clone https://github.com/docker/getting-started.git

## 2. Container Image 빌드하기

    1. git clone 한 getting-started/app 으로 이동(path)

        - cd ../../ getting-started/app

    2. 빈 파일 생성(Dockerfile) 및 Dockerfile 작성

        - type nul > Dockerfile

        - 파일작성  
            # syntax=docker/dockerfile:1
            FROM node:18-alpine
            WORKDIR /app
            COPY . .
            RUN yarn install --production
            CMD ["node", "src/index.js"]
            EXPOSE 3000

    3. Container Image 빌드하기

        - cd ../../ getting-started/app

        - docker build -t getting-started .

        >__docker build__ 명령어는 Dockerfile 을 사용하여 Container Image 를 빌드함. image 는 Dockerfile 의 FROM node:18-alpine 을 참조

# 2. Update Container

docker 는 이미 실행중인 Container 는 수정할수가없다. 따라서 기존 Container 를 제거하고 다시 Conatiner 를 생성해주면 된다.

## 1. 기존 container 제거
- 기존 container 의 id 가져오기 : $docker ps
- 기존 container id 를 중지하기 : $docker stop "the-container-id"
- 기존 container id 를 제거하기 : $docker rm "the-container-id"
* One line command : docker rm -f "the-container-id"

OR

- docker desktop 에서 쉽게 삭제하기

## 2. 새 container 생성

1.2.3 Container Image 빌드하기, 를 똑같이 실행

- docker build -t getting-started .
- docker run -dp 127.0.0.1:3000:3000 getting-started


# 3. Share the application

Docker image 를 공유하기 위해서는 Docker 등록이 필요하며, 기본 등록은 Docker hub. Docker ID 는 Docker hun

## 1. Docker hub 계정생성

[Docker-hub](https://hub.docker.com/)

## 2. repository 생성하기

    docker hub 에서 create repo

    or

    [CLI]
    docker tag local-image:tagname new-repo:tagname
    docker push new-repo:tagname


## 3. image 를 repo 에 push 하기

docker push eunseong98/getting-started(repo name):0.0.1(tagname)


## 4. 새 인스턴스에서 image 사용하기

docker build --platform linux/amd64 -t eunseong98/getting-started .
docker build -f "C:\Users\pogle\desktop\Personal Project\docker\getting-started\app\Dockerfile" .