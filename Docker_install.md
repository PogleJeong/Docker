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