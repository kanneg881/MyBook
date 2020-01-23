---
description: 適用於 bash 指令
---

# bash

`$ ifconfig`  
分析網路，檢測並與網路介面卡進行互動

`$ ls [-al] [path]`  
列出當前目錄中的檔案與子目錄  
-a 顯示隱藏檔案  
-l \(long listing\)詳細資料  
path 指定目錄

`$ ps [aux]`  
顯示所有系統上正在運行的程序  
a 顯示現有終端機下的所有程序，包括其他用戶的程序  
u 以用戶為主的格式來顯示程序狀況  
x 顯示所有程序，不以終端機來區分

`$ whoami`  
查看登入資訊

## 查看檔案

`$ head [-number] path/to/file`  
顯示檔案開頭 10 行  
-number 指定行數，例如 -20  
path/to/file 檔案位置

`$ less path/to/file`  
查看檔案內容  
按 `/` 可以搜尋關鍵字  
按 `n` 跳下一個  
英文有一句諺語 : less is more   
應對了  less 和 more 指令

`$ more path/to/file`  
查看檔案內容  
按 `<Enter>` 顯示下一行  
按 `q` 離開

`$ nl [option] path/to/file`  
顯示檔案內容，並顯示行號  
-ba 行數包含空白，預設不包含

`$ tail [-number] path/to/file`  
顯示檔案尾部 10 行  
-number 指定行數，例如 -20  
path/to/file 檔案位置

