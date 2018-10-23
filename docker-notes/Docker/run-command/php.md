# PHP

```
docker run -d -p 80:80 --name kaifeng-web -v /home/ftp/www:/var/www/html --link mysql:db php:7.2.0RC2-apache
```

# jxnewdate/php-ext

```
docker run -d -P --name php-server -v /homt/ftp/www:/var/www/html --link mysql:db jxnewdate/php-ext
```

