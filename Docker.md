Docker
=======

# 0. Container 란?


IT 기술에서의 Container 도 물류분야에서의 Container 처럼 이동성을 실현하기 위한 기술이다.
이는 어느 환경이나 인프라로든 쉽게 이동할 수 있는 장점을 가진다

>Application 을 실행하기 위한 컴퓨팅 작업을 패키징하여 Image 로 만들어 경량화된다.

>각각의 Container 는 종속성이 없고 서로 격리되어 있어 자기만의 독립적인 환경이 갖추어져있음.

>Server 나 OS 환경에 종속적이지 않아 Applictaion 이식성이 실현된다.

>>Application 이식성 : Container 가 작동하는 환경이라면 어디서든 작동가능함, 모든 OS 에서 사용가능

# 1. Docker Image

__Docker Container 를 만드는데 사용되는 읽기전용 템플릿__
Docker file 를 만든 후 빌드하여 Docker Image 를 만듦

+ Docker file - 컨테이너 실행에 필요한 파일과 설정값을 포함하는 파일

Docker Image 는 **Docker hub** 에서 자신이 필요한 소프트웨어에 맞게 pull 할 수 잇음.

# 2. Docker Container

Docker Image 가 실행한 상태, Docker Image 를 통해 Docker Container 생성
Docker Container 는 __Docker Image 에 목적에 맞는 파일 FS 과 격리된 시스템 자원 네트워크를 사용할 수 있는 독립된 공간 생성__

Docker Container 는 Docker Image 에서 하나의 Container Layer 에 저장됨.
(하나의 Docker Image 에 각각의 독립된 여러개의 Docker Container 가 저장되어있음)

>Docker Image 는 도넛레시피
>Docker Container 는 해당 레시피를 사용하여 만든 다양한 종류의 도넛

![Docker Image and Docker Container](https://tech.cloudmt.co.kr/2022/06/29/%EB%8F%84%EC%BB%A4%EC%99%80-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88%EC%9D%98-%EC%9D%B4%ED%95%B4-1-3-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88-%EC%82%AC%EC%9A%A9%EB%B2%95/images/image_container2.png)

>기존 Docker Image 를 수정해도 이미 실행중인 Docker Container 에는 영향을 주지 않음



참고자료
1. [클라우드메이트 TE팀 이도현](https://tech.cloudmt.co.kr/2022/06/29/%EB%8F%84%EC%BB%A4%EC%99%80-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88%EC%9D%98-%EC%9D%B4%ED%95%B4-1-3-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88-%EC%82%AC%EC%9A%A9%EB%B2%95/)
2. [클라우드메이트 - 컨테이너란?](https://cloudmt.co.kr/?p=3927)