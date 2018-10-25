# Telnet配置
为R1配置Telnet登录方式为密码验证登录，设置密码为“huawei”，定义用户权限级别为3。

```
[R1]user-interface vty 0 4
[R1-ui-vty0-4]authentication-mode password 
Please configure the login password (maximum length 16):huawei
[R1-ui-vty0-4]display this
[V200R003C00]
#
user-interface con 0
 authentication-mode password
user-interface vty 0 4
 authentication-mode password
 set authentication password cipher %$%$(4|m1iaM/F{=&tK2~]s>,#':5/1/AoTH26;HQ@YK
Z4bE#'=,%$%$
user-interface vty 16 20
#
return
[R1-ui-vty0-4]user privilege level 3
```

为R2配置Telnet登录方式为用户名+密码登录方式
```
[R2]user-interface vty 0 4
[R2-ui-vty0-4]authentication-mode aaa
[R2-ui-vty0-4]quit
[R2]aaa
[R2-aaa]local-user huawei password cipher huawei
[R2-aaa]local-user huawei privilege level 15
[R2-aaa]local-user huawei service-type telnet 
```