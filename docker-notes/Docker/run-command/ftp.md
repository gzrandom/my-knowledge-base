- # FTP
  - ## Pure-FTP
  ```
  docker run -d --name ftpserver -p 21:21 -p 30000-30009:30000-30009 -e "PUBLICHOST=localhost" -v /home/ftp:/home/ftpusers/abc jxnewdate/pure-ftp
  ```
  此镜像上自带ftp用户：abc，密码：123456
  主目录：/home/ftpusers
  每个用户在主目录下有自己名字的文件夹，即：
  abc用户：/home/ftpusers/abc