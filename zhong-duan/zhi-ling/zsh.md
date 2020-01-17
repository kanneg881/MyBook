---
description: 適用於 zsh 指令
---

# zsh

`$ cd directorName`  
移動到 directorName 資料夾

`$ cp file copyfile`  
複製一份 file 命名為 copyfile

`$ mkdir directorName`   
建立一個名為 directorName 資料夾

`$ ls [path] [-a] [-l]`  
列出 path 資料夾下的檔案和資料夾  
path 空白是當前位置的資料夾  
-a 列出隱藏資料夾和隱藏檔案  
-l 列出詳細資料

`$ ls [path] -al`  
也可以把參數寫在一起

`$ pwd`  
顯示當前目錄位置

`$ <Ctrl-c>`  
終止正在執行的程式

`$ <Ctrl-z>`  
暫停正在執行的程式，並且將程式被放到背景  
例如：終端輸入 `vim` 指令打開編輯後即可使用 `<Ctrl-z>`

`fg`  
繼續執行被暫停的程式，並且將程式被放到前景

## 目錄路徑

路徑有絕對路徑和相對路徑

絕對路徑：起始位置是根目錄的位置，根目錄前面沒有目錄了，  
一般都是 / 開頭

相對路徑：起始位置是相對於某個特定的位置

. 為相對路徑，指的是當前目錄底下  
~ 為相對路徑，指的是使用者目錄

假設使用者目錄在 /Users/Enjoy

```text
$ cd /Users
/Users

$ cd ./Enjoy
/Users/Enjoy

$ cd /
/

$ cd ~
/Users/Enjoy
```

