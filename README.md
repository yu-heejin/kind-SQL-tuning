## 실습 방법
> Oracle DB를 기준으로 실습합니다.
>
> MacOS에서 도커 이미지로 오라클 설치 시 Colima를 설치해야합니다. (https://king-ja.tistory.com/107)
>
1. docker pull jaspeen/oracle-xe-11g
2. docker run --name oracle11g -d -p 8080:8080 -p 1521:1521 jaspeen/oracle-xe-11g -e ORACLE_PASSWORD=pass
3. ocker exec -it oracle11g sqlplus

* 기본 비밀번호는 system/oracle

## scott 게정 활성화
* https://hyunki99.tistory.com/52

## 참고 자료
* https://king-ja.tistory.com/107
* https://velog.io/@hoplin/Docker%EB%A1%9C-Oracle-DB%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0
* https://dbwriter.io/oracle-installation-with-docker/
* https://hyunki99.tistory.com/52