---
title: Ubuntu-22.04配置IP
categories:
  - 系统
  - Ubuntu
tags:
  - ubuntu
date: 2023-06-26 01:49:58
---

# 步骤

```bash
$ ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp1s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 52:54:00:a1:f2:cb brd ff:ff:ff:ff:ff:ff
    inet 10.1.1.35/24 metric 100 brd 10.1.1.255 scope global dynamic enp1s0
       valid_lft 41800sec preferred_lft 41800sec
    inet6 fe80::5054:ff:fea1:f2cb/64 scope link 
       valid_lft forever preferred_lft forever
```

## 1. 修改配置

```bash
$ cat /etc/netplan/00-installer-config.yaml
# This is the network config written by 'subiquity'
network:
  ethernets:
    enp1s0:
      dhcp4: false
      addresses: [10.1.1.201/24]
      gateway4: 10.1.1.2
      nameservers:
        addresses: [10.1.1.2]
  version: 2
```

## 2. 应用

```bash
$ netplan apply
$ ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp1s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 52:54:00:a1:f2:cb brd ff:ff:ff:ff:ff:ff
    inet 10.1.1.201/24 brd 10.1.1.255 scope global enp1s0
       valid_lft forever preferred_lft forever
    inet6 fe80::5054:ff:fea1:f2cb/64 scope link 
       valid_lft forever preferred_lft forever
```

