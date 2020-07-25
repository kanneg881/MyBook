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

`$ sed s/keyword/replace/g path/to/file > path/to/newFile`  
尋找位於 path/to/file 檔案的 keyword 內容並取代成 replace  
然後另存為  path/to/newFile  
s/keyword/replace/g 的 s 為搜尋  
s/keyword/replace/g 的 g 為全域搜尋  
如果沒有 g 則只取代搜尋到的第一個  
如果 g 改成數字 n，則指定取代搜尋到的第 n 個

## 破壞檔案

當你要徹底移除檔案，你只使用刪除，有可能還是會被復原  
最好的辦法是，刪除一個檔案，在覆寫數次，這樣復原的難度就會提高好多

`$ shred -f -n number /path/to/file`  
複寫 /path/to/file 檔案 number 次  
-f 修改檔案權限，讓你可以覆寫  
-n number 覆寫 number 次  
/path/to/file 檔案位置

## 目錄

`$ cd -`  
移動到上一個切換的資料夾

`$ cd directoryName`  
移動到 directoryName 資料夾

`$ mkdir directoryName`  
新增目錄

`$ rmdir directory`  
刪除空目錄

`$ rm -r directory`  
刪除目錄和目錄底下所有檔案  
**注意 : 使用此指令一定要確認好路徑位置**  
如果刪錯路徑會遺失很多重要資料  
以前作者就曾誤刪根目錄 rm -r / \(千萬不要使用此指令\)  
誤刪根目錄有很多系統的檔案，誤刪會造成系統發生異常  
所以要特別小心

