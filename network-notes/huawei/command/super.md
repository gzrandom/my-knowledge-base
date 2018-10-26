# super
功能：配置设备的超级密码。在用户权限较低时（例如Telnet登录时，可以定义权限级别为0或1），此时可以使用super命令进行权限提升。为避免非法权限提升带来的危害，应该配置超级密码进行防护。

视图：系统视图

```
[R2]super password cipher huawei
[R2]display current-configuration 
#
sysname R2
#
super password level 3 cipher \p9d>[S5T/@X,k6.E\Z,8L{#
#
```