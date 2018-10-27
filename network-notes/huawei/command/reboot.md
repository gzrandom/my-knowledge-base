# reboot
功能：重启路由器

视图：用户视图

```
<R1>reboot
Info: The system is now comparing the configuration, please wait.
Warning: All the configuration will be saved to the configuration file for the n
ext startup:, Continue?[Y/N]:n
Info: If want to reboot with saving diagnostic information, input 'N' and then e
xecute 'reboot save diagnostic-information'.
System will reboot! Continue?[Y/N]:y
Oct 27 2018 10:54:53-08:00 R1 %%01CMD/4/REBOOT(l)[1]:The user chose Y when decid
ing whether to reboot the system. (Task=co0, Ip=**, User=**)
<R1>
```
重启时系统会提示是否需要保存当前配置，根据实际需要选Y/N就可以。