# VLAN 虚拟局域网
1. vlan基本配置

   1.1. 组网及业务描述
![vlan](../pics/vlan-001.jpg "vlan基本设置001")
在同一交换机内同一vlan的PC可以互通，不同vlan的PC不可互通。

   1.2. 命令行列表
   
   操作|命令
   ---|---
   创建vlan|vlan *vlan-id* [alias vlan-alias]
   删除vlan|undo vlan *vlan-id* [\|all]
   vlan视图下配置一个或者一组端口属于某个vlan|port interface-type {interface-num [to interface-num]}&<1-10>
   接口视图下配置该端口属于某个vlan|port access vlan *vlan-id*



## 2. Trunk基本配置
## 3. vlan间的三层互通