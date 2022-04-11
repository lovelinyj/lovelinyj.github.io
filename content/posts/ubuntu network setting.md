---
title: "ubuntu network setting"
date: 2022-04-11T23:07:03+08:00
type: post
---
# ubuntu network setting

# 手動設定

1. 確認網卡介面
> `ip add`

2. 新增固定IP
> `sudo ip address add 10.102.66.200/24 dev [interface]`

3. 重啟網卡介面
> `ip link set dev [interface] down`
> `ip link set dev [interface] up`

4. 設定預設路由
> `sudo ip route add default via 10.102.66.1`

5. 新增DNS
> `sudo nano /etc/resolv.conf`
> 新增
> `nameserver 8.8.8.8`


# 開機自動設定IP
1. 修改netplan
> `sudo nano /etc/netplan/99_config.yaml`
> 設定下列內容
>> network:
>>  version: 2
>>  renderer: networdd
>>  ethernets:
>>   eth0:
>>    addresses: [10.10.10.2/24]
>>    gateway4: 10.10.10.1
>>    nameservers:
>>     addresses: [10.10.10.1]

2. 執行網路計畫
> `sudo netplan apply`