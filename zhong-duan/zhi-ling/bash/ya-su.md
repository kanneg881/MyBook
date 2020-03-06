# 壓縮與打包

## 打包

### tape archive \(tar\)

打包檔案，打包好會比原本的檔案還大

`$ tar -cvf fileName.tar file1 [file2 [file3]]`  
打包檔案  
-c 建立檔案  
-v 列出 tar 指令處理的檔案 \(不想列出可省略\)  
-f 指名打包後的檔案名稱也具備讀取檔案的功能

`$ tar -tvf fileName.tar`  
-t 顯示檔案內容

`$ tar -xvf fileName.tar`  
-x 解打包檔案

## 壓縮

將檔案變小的技術

壓縮速度  
compress &gt; gzip &gt; bzip2

壓縮大小  
 compress &gt; gzip &gt; bzip2

### GNU zip \(gzip\)

`$ gzip fileName`  
壓縮檔案



