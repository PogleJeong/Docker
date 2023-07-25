Docker 실행 시 발견한 Error 해결 정리
======


error during connect: This error may indicate that the docker daemon is not running. The system cannot find the file specified.
======

docker desktop 에서 setting 변경

setting - General - **Expose daemon on tcp://localhost:2375 without TLS** 체크


An image does not exist locally with the tag: ~
======

docker hub 의 repository 이름과 local에 있는 docker image 의 repsitory 이름이 달라서 생기는 오류, 둘이 이름이 같아야 push 가능