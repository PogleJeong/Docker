Docker file & build
======

Docker image 를 생성하기 위해서는 2가지 방법이 있다.

첫번째 방법은 image 를 이용해 container 를 만들고 container 를 commit 작업을 해서 만드는 방법이다.

이 방법은 사용하고 있는 container 를 image 로 생성하는 백업같은 느낌의 방법이다.

두번째 방법은 Dockerfile 을 생성하고 작성하여 build 하는 방법이다.

이 방법은 체계적으로 명시하여 생성하는 느낌이다. 해당 image 가 어떻게 구성되었는지 알 수 있다.

# 0. Dockerfile

FROM (image)      > pull 할 image
RUN apt update && apt install -y python3    > container에서 실행할 명령어 작성
WORKDIR /var/www/html    > 해당경로로 디렉토리를 생성 후 이동시킴
COPY ['index.html','.']    > host에 존재하는 index.html을 현재 디렉토리(".")로 복사
CMD ["python3", "-u", "-m", "http.server"]


# 1. RUN vs CMD

RUN : IMAGE 가 build 되는 시점에 실행. - image 에 반영
CMD : container 가 실행될 때 실행됨. - container 에 반영