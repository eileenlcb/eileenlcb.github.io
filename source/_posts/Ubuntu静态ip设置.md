---
title: Ubuntu静态ip设置
date: 2019-09-26 17:51:38
password: lcb.771383
tags: 总结
---

1.通过~~ifconfig~~``ip link show``查询本机网络接口，比如`enp7s0`

2.打开网络修改文件 
`sudo gedit /etc/network/interfaces`，增加以下部分
```
auto enp7s0
iface enp7s0 inet static
address 10.0.208.222
netmask 255.255.240.0
gateway 10.0.208.1
dns-nameservers 10.0.208.1
```

3.刷新ip
```
sudo ip addr flush enp7s0
sudo systemctl restart networking.service
```

4.重启电脑后修改`sudo gedit /etc/NetworkManager/NetworkManager.conf`
将`managed=false`修改为`managed=true`。然后重启服务`sudo service network-manager restart`。
