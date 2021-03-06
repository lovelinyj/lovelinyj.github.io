---
title: "Linux的ln捷徑設定教學"
date: 2022-03-17T08:28:27+08:00
type: post
tags: [linux]
---

使用ln建立連結檔案有兩種方式

1. **硬連結**
2. **軟連結**

---

#### 建立硬連結
> 使用相同的inode的連結檔案
>
> `ln 123.txt 123_ln.txt`
>
> `ln [來源檔案位置] [捷徑檔案位置]`

硬連結無法連結一個資料夾

---
#### 建立軟連結

>靠著絕對路徑或相對路徑來指向目標檔案的連結檔
>
> `ln -s 123.txt 123_ln.txt`
>
> `ln -s [來源檔案位置] [捷徑檔案位置]`

若要取消軟連結，可使用

> `unlink 123_ln.txt`

---

在預設狀況下，若連結已經存在，建立連結檔案時會出現錯誤。

> `ln -s 123.txt 123_ln.txt`
>
> `ln: failed to create symbolic link '123_ln.txt': 檔案已存在`

若要強制覆蓋舊連結，須加上 **`-f`** 參數

> `ln -f -s 123.txt 123_ln.txt`

除了強制覆蓋外，也可以使用 **`-b`** 參數，將舊連結檔案備份，再建立新連結檔。

> `ln -b -s 123.txt 123_ln.txt`

ln 會將原本的檔案名稱後方加上 **`~`** ，作為檔名

若要更改備份檔案名稱的結尾，可使用 **`-S`** 參數指定新名稱

> `ln -b -S ".backupfile" -s 123.txt 123_ln.txt`