# 数据容器+MYSQL+WORDPRESS

## 数据容器

```
docker run -d --name dbdata -v /var/lib/mysql ubuntu
```

## MYSQL

```
docker run -d --name mysql --volumes-from dbdata -e MYSQL_ROOT_PASSWORD=654321 -e MYSQL_DATABASE=kaifeng -e MYSQL_USER=kaifeng -e MYSQL_PASSWORD=123456 mysql
```

## WORDPRESS

```
docker run -d --name=kaifeng-web -v /home/lhy/www:/var/www/html --link dbs:db -p 80:80 wordpress
```



