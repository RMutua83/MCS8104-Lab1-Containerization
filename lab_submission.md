# Lab 1: Containerization

## 1. Docker command to create and run a container named `dbserver-mysql-nairobi`

Use the `customized-ubuntu:1.0` image to create a container named `dbserver-mysql-nairobi`. The command should map the container’s port 3306 to the host’s port 3309.

```dockerfile
Specify your commands here

docker build -t customized-ubuntu:1.0 ./images/ubuntu
docker run -dit --name dbserver-mysql-nairobi -p 3309:3306 customized-ubuntu:1.0

```

## 2. MySQL Server and MySQL Client Installation in Ubuntu

```shell
Specify your commands here

docker exec -it dbserver-mysql-nairobi bash
apt update
apt install mysql-server mysql-client -y
service mysql start

```

## 3. Login using the MySQL Client and Change the MySQL Root Password

```sql

mysql -u root
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '5trathmore';
FLUSH PRIVILEGES;
EXIT;

```
docker commit dbserver-mysql-nairobi dbserver-mysql-nairobi
docker stop dbserver-mysql-nairobi
docker start dbserver-mysql-nairobi
docker attach dbserver-mysql-nairobi
service mysql start
mysql -u root -p
# ( password: 5trathmore)