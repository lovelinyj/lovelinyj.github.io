---
title:  "使用jekyll-theme-chirpy主題建立Github Page"
date: 2026-03-18T16:48:43+08:00
layout: post
tags: [github]
categories: Github
---
# 使用jekyll-theme-chirpy主題建立Github Page
1. 拉取儲存庫
```
git clone https://github.com/cotes2020/jekyll-theme-chirpy.git
```
3. 在根目錄中執行以初始化儲存庫
```
cd ./jekyll-theme-chirpy
bash tools/init.sh
```
Node.js version >= 20
4. 在倉庫根目錄下執行命令以安裝相依性
```
bundle config set --local path 'vendor/bundle'
bundle install
```
1.  啟動 Jekyll 伺服器
```
bundle exec jekyll serve
```
# 上傳到Github
1. 確認遠端儲存庫地址
首先，檢查目前的目錄指向哪裡。輸入：
```
git remote -v
```
如果看到的不是 lovelinyj/lovelinyj.github.io.git，請執行以下指令來更換遠端地址：

### 移除目前的遠端設定
```
git remote remove origin
```

### 加入你自己的 GitHub 儲存庫（請將 lovelinyj 換成你的帳號名）
```
git remote add origin https://github.com/<username>/<username>.github.io.git
```
2. 強制提交（解決 Husky 報錯）
剛才因為 husky 檢查訊息格式導致失敗，為了快速完成，我們直接跳過檢查進行提交：

Bash
###  加入所有檔案
```
git add .
```

### 2. 提交訊息（加上 --no-verify 跳過格式檢查）
```
git commit -m "chore: initial chirpy theme setup" --no-verify
```
### 推送到 GitHub
這步最關鍵。因為你的 lovelinyj.github.io 原本就有資料，Git 可能會報錯說「兩邊歷史不一致」。我們使用 --force（強制推送）來讓你的遠端儲存庫完全同步為現在這個 Chirpy 版本：


### 強制推送到 main 分支
```
git push -u origin main --force
```