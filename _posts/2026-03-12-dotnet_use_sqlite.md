---
title: "Dotnet Core使用SQLite資料庫"
date: 2026-03-12T16:48:43+08:00
layout: post
tags: [coding]
categories: Coding Dotnet
---
## 最近在學習用dotnet core寫自己的網頁，小型服務基本上用SQLite當作資料庫就可以了
### 1.vscode在終端機執行
`dotnet new blazor -e -o ./{專案名稱}`
### 產生一個blazor專案，`-e`指的是`--empty`，產生空的專案，`-o`是`--output`指定專案的資料夾位置
### 2.產生後執行
`dotnet add package Microsoft.EntityFrameworkCore.Sqlite`
`dotnet add package Microsoft.EntityFrameworkCore.Design`
### 將專案新增SQLite需要的套件