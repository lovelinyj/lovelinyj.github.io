---
title:  "Linux 磁碟空間分析神器：ncdu"
date:   2026-03-19 16:42:18 +0800
layout: post
tags: [software]
categories: Software Ncdu
---
# [工具推薦] Linux 磁碟空間分析神器：ncdu
在維護 Linux 伺服器或開發環境（如 WSL）時，最常遇到的問題就是「硬碟空間又滿了」。
雖然傳統的 `du -sh` 指令可以用，但要一層層進去檢查實在太慢。今天要推薦的是一款兼具視覺化與互動性的終端機工具：ncdu (NCurses Disk Usage)。

## 1. 什麼是 ncdu？
ncdu 是 du 指令的進階版，它基於 ncurses 函式庫開發，提供了一個文字介面的互動式選單。它能掃描你的資料夾，並依據大小排序，讓你一眼看出是哪個「空間殺手」佔用了硬碟。
## 2. 安裝方式
在大多數的 Linux 發行版中，ncdu 都可以透過套件管理員快速安裝：

- Ubuntu / Debian / WSL:

```Bash
sudo apt update
sudo apt install ncdu
```
- CentOS / RHEL:

```Bash
sudo yum install ncdu
```
- macOS (Homebrew):

```Bash
brew install ncdu
```

## 3. 基本使用指令
A. 掃描當前資料夾
最簡單的用法，直接在想檢查的目錄輸入：

```Bash
ncdu
```
B. 掃描整個系統
如果你想從根目錄開始檢查（需要 sudo 權限）：

```Bash
sudo ncdu /
```
## 4. 互動操作快捷鍵進入
 ncdu 的掃描畫面後，你可以使用以下按鍵進行操作：
 |按鍵|功能說明|
 |---|---|
 |上下鍵 / j, k|移動游標選擇資料夾或檔案|
 |Enter / 右鍵|進入該資料夾查看細節|
 |Left / h|回到上一層目錄|
 |n|依名稱排序 (Name)|
 |s|依大小排序 (Size)|
 |d|刪除所選的檔案或資料夾 (會跳出確認視窗)|
 |g|切換顯示模式 (百分比、圖表、或兩者皆顯示)|
 |q|離開 ncdu|