---
title: 大并发流量下kafka节点如何安全拉起
date: 2019-09-14 22:21:38
tags: kafka
---
# Q：在大规模kafka集群中(网络流量很大)，一个节点down掉如何正确并安全的恢复？

### 1、通过iptables和ipset限制端口访问量(success)
```
# !/bin/bash

yum -y install ipset

ipset create nodes hash:ip 

netstat -anp|grep xx.xx.xxx.xx:9092 |awk {'print $5'}|head -10000|sort -n| uniq |cut -f4 -d":" > kafka-ipv4.txt

cat kafka-ipv4.txt | while read line
do 
	ipset add nodes $line
done

iptables -I INPUT -m set --match-set nodes src -p tcp --destination-port 9092 -j DROP
service iptables save
service iptables restart

```

### 2.supervisord启动kafka

`supervisorctl start kafka `
控制台可能卡住，直接ctrl+c即可

### 3.ipset逐渐放量
```
# !/bin/bash

sed -n '2,2000p' kafka-ipv4.txt > kafka_accept_1.txt

cat kafka_accept_1.txt | while read line 
do
	ipset del nodes $line
done

service iptables save
service iptables restart

```

### 4.反复执行步骤3
`2,2000`到`8000,10000`

### 5.关闭防火墙
`service iptables stop`
此时节点已完全恢复