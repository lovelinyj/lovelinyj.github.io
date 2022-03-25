---
title: "Clear Github Branch"
date: 2022-03-17T12:42:13+08:00
type: post
tags: [github,clear_branch]
---

# 清除gh_pages的資料

first, chang branch to gh-pages

	git checkout gh-pages

clear all data

	git rm -rf .

than push to reponsitory

	git add .

	git commit -m "clear gh-pages

	git push origin gh-pages