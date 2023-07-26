docker-compose.yml
======

어려운 명령어 대신 깔끔하게 명세를 적을 수 있도록 도와준다.

또한 docker-compose.yml 를 작성하고

$ docker-compose up 명령어 실행시 docker-compose.yml 에서 작성한 대로 container 가 생성된다.


version:   > 버젼정보

services:   > 작성하고 싶은 container 정보
    db:
        image:    > container가 가질 image
        volumnes: ./db_data:/var/lib/mysql   
        >  내 로컬의 db_data 파일과 container 의 파일을 연결, 데이터유실방지
        environment:    > DB 정보

    app:
        depends_on:     > 선행되어야할 container 작성
        image:     > depends_on 에 명시된 container 생성 이후 실행
        volumes:
        ports:    
        environment:
            WORDPRESS_DB_HOST: db:3306

            **같은 네트워크에 접속되어있는 db 라는 이름의 container 를 찾아 3306 port 받음.**

[생활코딩](https://www.youtube.com/watch?v=EK6iYRCIjYs)