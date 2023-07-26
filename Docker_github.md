github 로 Docker image 공유하기
======

github 의 profile 에서 Package 들어가기

Choose a registry 에서 Docker 가 아닌 COntainers 선택


# 1. Personal access tokens(PAT) 받기

profile - settings - Developer settings - Personal access tokens

packages 로 보낼때 인증할 token 발급받음.

Notes, Expriation, Select scopes 설정 필요

[select scopes]
write:packages 체크
delete:packages 체크

Generate token 으로 발급받기

# 2. PAT 를 로컬의 환경변수로 설정 및 로그인

export $CR_PAT="발급받은 PAT"
echo $CR_PAT | docker login ghcr.io -u USERNAME --password-stdin
> login success

# 3. image push
docker push ghrc.io/USERNAME/IMAGE-NAME:TAG


# 4. packages 에서 확인

# 5. Git repo 와 packages 연결

create repo 이후 Packages 로 이동하여 connect Repository 클릭