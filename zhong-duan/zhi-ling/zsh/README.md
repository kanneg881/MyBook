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

`$ ls [-al] [path]`  
列出當前目錄中的檔案與子目錄  
-a 顯示隱藏檔案  
-l \(long listing\)詳細資料  
path 指定目錄

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

```text
$ alias tree="find . -print | sed -e 's;[^/]*/;|____;g;s;____|; |;g'"
終端畫面的目錄樹別名
```

