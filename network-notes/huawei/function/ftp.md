# FTP (未完成)
功能：使用FTP在路由间上传下载文件

下面的例子中R1作为FTP客户端（路由器默认即为FTP客户端），R2作为FTP服务器端。

```
[R2]ftp server enable  //开启FTP服务
Info: Succeeded in starting the FTP server.
[R2]set default ftp-directory sd1:/  //设置FTP根目录
[R2]aaa
[R2-aaa]local-user ftpuser password cipher huawei  //新建用户
[R2-aaa]local-user ftpuser service-type ftp  //指定用户类型为FTP
[R2-aaa]local-user ftpuser privilege level 3  //设置权限级别，级别不能高于当前登录用户
[R2-aaa]
```

```
<R1>
```