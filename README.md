# 管理机配置


生成ssh-key密钥对，分发公钥到各个主机（包括自己）

## 0.配置repo和epel源



## 1.管理主机安装ansible

```
[root@m01 ~]# yum install -y ansible python-pip
#安装环境
[root@m01 ~]# pip install redis
#升级pip
[root@m01 ~]# pip install --upgrade pip
```



## 2.防火墙设置（配置网卡区域，开启ip伪装）

```
[root@osker ~]# systemctl restart firewalld
#将wan网卡加入到external区（此区默认开启masquerade）
[root@osker ~]# firewall-cmd --add-interface=eth1 --zone=external
[root@osker ~]# firewall-cmd --add-interface=eth1 --permanent --zone=external

#将lan网卡加入到trusted区（trusted区默认拒绝所有，ssh除外）
[root@osker ~]# firewall-cmd --add-interface=eth0 --zone=trusted
[root@osker ~]# firewall-cmd --add-interface=eth0 --permanent --zone=trusted
```



## 3.上传ansible一件部署代码

## 4.修改/etc/hosts文件（解析全网ip与规划的主机名），拷贝到ansible中的default/files/hosts文件

## 5.修改ansible中的主机清单文件hosts（对应ip）

## 6.运行ansible-playbook 1. 2. 3. 4. 