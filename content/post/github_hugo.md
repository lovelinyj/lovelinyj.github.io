---
title: "運用github建立個人部落格，使用hugo"
date: 2022-03-17T08:28:27+08:00
draft: false
---

建立一個自己的部落格其實不難

1. 運用hugo建立部落格資料夾

`hugo new site lovelinyj.github.io`

2. 進到該資料夾

`cd lovelinyj.github.io`

3. git初始化

`git init`

4. 套用hugo樣式

`git submodule add https://github.com/lxndrblz/anatole.git themes/anatole`

5. 修改config.toml

增加`themes= "anatole"

6. 新增部落格文章

`hugo new post/first.md`

7. push到github上

`git add.`
`git commit -m 'new blog'`
`git push origin main`
