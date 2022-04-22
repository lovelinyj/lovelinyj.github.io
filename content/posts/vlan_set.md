---
title: "Vlan_set"
date: 2022-04-11T23:07:03+08:00
type: post
---

# 查詢vlan設定  
> Switch#show vlan brief 


# 建立VLAN
> Switch(config)#vlan 10  
Switch(config-vlan)#name Attack  
Switch(config)#interface range gigabitEthernet 1/0/1-9  
Switch(config-if-range)#switchport  access  vlan 10  

# 設定DHCP helper-address
> Switch(config)#int vlan 10  
Switch(config-if)#ip helper-address 192.168.100.200  


