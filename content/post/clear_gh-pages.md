---
title: "Clear_gh Pages"
date: 2022-03-17T12:42:13+08:00
type: post
---

清除gh_pages的資料
首先將branch移至gh-pages
`git checkout gh-pages`
然後清空資料
`git rm -rf .`
接著push上去reponsitories
`git add .`
`git commit -m "clear gh-pages`
`git push origin gh-pages`