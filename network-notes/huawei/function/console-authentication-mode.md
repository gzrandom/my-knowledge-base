# 配置Console口登录认证方式及超时时间
默认情况下，通过Console口登录无密码

```
<Huawei>system-view  
[Huawei]user-interface console 0  //进入Console接口视图
[Huawei-ui-console0]authentication-mode password  //设置认证方式为密码
[Huawei-ui-console0]set authentication password simple huawei  //设置密码为明文的huawei
[Huawei-ui-console0]idle-timeout 20 0  //设置空闲超时时间为20分钟（20为分钟，0为秒）
```