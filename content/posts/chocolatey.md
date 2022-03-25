---
title: "Chocolatey"
date: 2022-03-25T10:23:26+08:00
type: post
tags: [chocolatey,software]
---

# Chocolatey

工具介紹：
	
>	chocolatey是一個windows使用的套件管理工具  
	就像是linux的apt,pcman等等  
	不妨試試看
	
	
安裝方式：
	
>	在powershell中輸入  

	Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
	
### [官方網站](ttps://chocolatey.org/)