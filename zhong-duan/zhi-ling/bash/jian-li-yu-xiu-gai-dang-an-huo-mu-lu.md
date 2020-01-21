# 建立與修改檔案或目錄

## 檔案

`$ cat fileName`  
顯示檔案

`$ cat > fileName`  
建立檔案，之前的內容會覆蓋  
輸入完內容按 `<Ctrl-D>` 回到終端

`$ cat >> fileName`  
建立檔案，內容添加在原檔案後方  
輸入完內容按 `<Ctrl-D>` 回到終端

`$ touch fileName`  
建立新檔

`$ cp file path/to/copyFile`  
複製一份 file 命名為 copyFile 到指定目錄  
不指定目錄就是在當前目錄  
不指定檔案名稱就是原檔名  
不能都不指定

`$ mv file newFile`  
重新命名 file 為 newFile  
mv 是搬移指令，搬移目錄或檔案  
用這個方法來重新命名

`$ rm file`  
移除檔案

## 目錄

`$ mkdir directoryName`  
新增目錄

`$ cd directoryName`  
移動到 directoryName 資料夾

`$ rmdir directory`  
刪除空目錄

