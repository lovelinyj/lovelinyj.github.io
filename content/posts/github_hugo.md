---
title: "使用Hugo在Github上建立個人部落格"
date: 2022-03-17T08:28:27+08:00
type: post
tags: [github,hugo]
---

建立一個自己的部落格其實不難

1. 運用hugo建立部落格資料夾

	`hugo new site lovelinyj.github.io`

2. 進到該資料夾

	`cd lovelinyj.github.io`

3. git初始化

	`git init`

4. clone submodule

	`git submodule add https://github.com/526avijitgupta/gokarna.git themes/gokarna`
	or
	`git clone https://github.com/526avijitgupta/gokarna.git themes/gokarna`
5. 修改config.toml

	增加一行`themes= "gokarna"`

6. 新增部落格文章

	`hugo new post/first.md`

7. push到github上

	`git add.`
	
	`git commit -m 'new blog'`
	
	`git push origin main`
	
		#### 詳細說明請參照github
		https://gokarna-hugo.netlify.app/posts/theme-documentation-basics/
		
