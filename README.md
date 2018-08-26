# 빠르게 살펴보는 Azure PaaS를 활용한 인프라 스트레스없는 웹서비스 배포

사용하는 Azure 서비스

+ Azure Storage: https://azure.microsoft.com/ko-kr/services/storage/
+ Azure Database for PostgreSQL: https://azure.microsoft.com/ko-kr/services/postgresql/
+ Azure Containers for Web App: https://azure.microsoft.com/ko-kr/services/app-service/containers/

본 장고 프로젝트에서 필요한 환경변수

+ Azure Storage 의 접근 정보
    - `AZURE_ACCOUNT_NAME`
    - `AZURE_ACCOUNT_KEY`
+ Database 접근 정보
    - `DB_HOST`
    - `DB_NAME`
    - `DB_USER`
    - `DB_PASSWORD`

## Docker 빌드 및 실행

Docker 빌드

```sh
docker build -t DOCKERHUB아이디/이름:태그 .
```

빌드한 이미지로 실행해보기 (환경변수들은 모두 채워주세요.)

```sh
docker run \
    -e AZURE_ACCOUNT_NAME="" \
    -e AZURE_ACCOUNT_KEY="" \
    -e DB_HOST="" \
    -e DB_NAME="" \
    -e DB_USER="" \
    -e DB_PASSWORD="" \
    -p 8080:80 \
    --rm -it \
    DOCKERHUB아이디/이름:태그
```

빌드한 이미지로 실행해보기 (환경변수들은 모두 채워주세요.)

```sh
# 맥/리눅스 용

docker run \
    -e AZURE_ACCOUNT_NAME="" \
    -e AZURE_ACCOUNT_KEY="" \
    -e DB_HOST="" \
    -e DB_NAME="" \
    -e DB_USER="" \
    -e DB_PASSWORD="" \
    -p 8080:80 \
    --rm -it \
    DOCKERHUB아이디/이름:태그
```

hub.docker.com 회원가입 후에, 빌드한 이미지를 Docker Hub에 업로드하기

```sh
docker login
docker push DOCKERHUB아이디/이름:태그
```

Azure Containers for Web App

+ 생성하고
+ `컨테이너 이미지`로 `DOCKERHUB아이디/이름:태그` 지정
+ Application Settings에서 위의 환경변수 지정

## 강의 VOD

+ [빠르게 살펴보는 Azure PaaS를 활용한 인프라 스트레스없는 웹서비스 배포](https://www.askcompany.kr/r/sections/7d64b4a/) VOD

## Copyright

+ © 2016~2018 Ask Company
+ 공식 사이트: [https://www.askcompany.kr](https://www.askcompany.kr)
+ Ask Django FB Group: [https://fb.com/groups/askdjango](https://fb.com/groups/askdjango)
    - 모든 파이썬/장고 질문이여. 오라 !!! :D
+ 강의문의: me@askcompany.kr

