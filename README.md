## 실습 방법
> Oracle DB를 기준으로 실습합니다.
>
> MacOS에서 도커 이미지로 오라클 설치 시 Colima를 설치해야합니다. (https://king-ja.tistory.com/107)
>
### Docker 환경 설정
1. colima start --memory 4 --arch x86_64
2. docker pull jaspeen/oracle-xe-11g
3. docker run --name {컨테이너 이름} -d -p 8080:8080 -p 1521:1521 jaspeen/oracle-xe-11g
    * docker logs -f {컨테이너 이름} : 오라클 성공 로그가 뜰 때까지 대기
4. docker exec -it {컨테이너 이름} sqlplus
    - 초기 아이디 / 비밀번호 : system / oracle

### scott 계정 사용하기
ALTER USER scott ACCOUNT UNLOCK;  
ALTER USER scott IDENTIFIED BY tiger;  
docker exec -i {컨테이너명} sqlplus system/oracle < {scott.sql 경로}  
docker exec -it {컨테이너 이름} sqlplus scott/tiger

 ## 오류 발생 및 해결
 * docker: Cannot connect to the Docker daemon at unix:///Users/hee/.colima/default/docker.sock. Is the docker daemon running?.
    1. colima stop
    2. colima start --memory 4 --arch x86_64


## 참고 자료
* https://devtagebuch.tistory.com/12
* https://proni.tistory.com/entry/Oracle-scott-%EC%8A%A4%ED%82%A4%EB%A7%88-%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0-%E3%85%A0-at-Mac
