## MYSQL 도커파일 생성방법

```txt
FROM mysql

ENV MYSQL_USER=ssar
ENV MYSQL_PASSWORD=ssar1234
ENV MYSQL_ROOT_PASSWORD=root1234
ENV MYSQL_DATABASE=ssardb

CMD ["--character-set-server=utf8mb4", "--collation-server=utf8mb4_unicode_ci"]
```

## 이미지 만들기

* Dockerfile이 있는 경로로 이동해서, 다음 명령 실행:

```
docker build -t mysql-image .
```

## UTF-8 설정확인

```sh
SHOW VARIABLE LIKE 'character_set_%';
```

## 볼륨 옵션으로 호스트 폴더에 연결해서 실행하는 명령

```sh
docker run -d -v C:\temp\docker_lab\ex05\mysql-volume:/var/lib/mysql -p 3306:3306 --name mysql-container mysql-image
```

## 이름이 있는 볼륨 사용법

```sh
docker run -d -v mysql-volume:/var/lib/mysql -p 3306:3306 --name mysql-container mysql-image
```
