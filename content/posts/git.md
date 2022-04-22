---
title: "Git"
date: 2022-04-22T13:40:37+08:00
type: post
---

# Git指令教學

## 開啟git tutorial
> `git help tutorial`

### 查詢log
> 圖形化顯示log  
> `git log --graph`

## 建立新專案
> 初始化  
> `$ git init`  
> 您現在已經初始化了工作目錄——您可能會注意到創建了一個名為“.git”的新目錄。  
> 
> 使用git add告訴Git對當前目錄下所有文件進行快照  
> `$ git add .`  
> 此快照現在存儲在 Git 稱為“index”的臨時暫存區域中。  
> 
> 您可以使用 git commit 將索引的內容永久存儲在存儲庫中：  
> `$ git commit`  
> 這將提示您輸入提交消息。您現在已將項目的第一個版本存儲在 Git 中。  
### 設定global
在進行任何操作之前，最好使用您的姓名和公共電子郵件地址向 Git 介紹自己。  
`$ git config --global user.name "Your Name Comes Here"`  
`$ git config --global user.email you@yourdomain.example.com`
