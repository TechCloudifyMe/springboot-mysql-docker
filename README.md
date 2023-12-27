# springboot-mysql-k8

## springboot-mysql deployment with docker
  - install git
  - install maven
  - install docker
### create a package using following commands
```
git clone <repalce-your-git-url>
mvn clean istall
```
### create a dokcer network
```
docker network create springboot-mysql-net
docker network ls
```
### create a docker image and create a docker container
- create mysql container
```
docker run --name mysqldb --network springboot-mysql-net -e MYSQL_ROOT_PASSWORD=Admin#123 -e MYSQL_DATABASE=employeedb -d mysql
```
- check application.properties file and change database details accordingly
```
cat /src/main/resources/application.properties
```
- create docker container
```
docker run --network springboot-mysql-net --name springboot-mysql-container -p 33333:33333 -d techcloudifyme/springboot-mysql:v4
```
**important Note** mysql container and docker container should be on same network
