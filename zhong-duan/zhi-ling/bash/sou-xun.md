# 搜尋

## find

`$ find directory options expression`

directory 目錄  
options 選項  
expression 表達式

進階搜尋

指定搜尋的起點目錄，檔案名稱、  
建立或修改日期、擁有者、群組、權限、大小等

`$ find ./ -atime -1`  
搜尋24小時內取用過的檔案

`$ find / -exec {command} \;`  
搜尋根目錄，並將找到的每一個檔案執行 {command} 指令  
\; 為結束

`$ find ./ -mmin -5`  
搜尋5分鐘內更改過的檔案

`$ find ./ -mtime -1`  
搜尋24小時內改過的檔案

`$ find ./ -mtime +1`  
搜尋超過24小時已修改的檔案

`$ find ./ -name 'fileName'`  
搜尋 fileName 檔名

`$ find / -type f`  
搜尋根目錄，類型為檔案

`$ find ./ -type f -exec file '{}' \; | egrep 'PNG' | cut -d' ' -f1`  
遞迴搜尋此目錄下的檔案，類型為 PNG，並只輸出檔案路徑

`find . -type f -user {userName}`  
搜尋持有者為 userName 的檔案

`$ finde /home -size +5G`  
搜尋 /home 目錄，大於 5G 的檔案

## grep

`$ grep [--line-buffered][-a][-i][-n][-r][-w] path [-e] keyword`  
過濾輸出或者檔案內容  
--line-buffered 每換行就將結果送至標準輸出，否則會等緩衝區滿才送  
-a 二進位可執行檔視為文字檔  
-i 不分大小寫  
-n 顯示行數  
-r 遞迴搜尋  
-w 比對完整的一個字  
path 搜尋路徑  
-e 指定正規表示式  
keyword 搜尋字串

egrep 等同於 grep -e

`$ grep -o 'regular expression' fileName`  
用只有符合正規表示式的值才會回傳  
而不會回傳整行資料  
-o 代表只有符合正規表示式的值才會回傳  
fileName 檔案名稱

`$ grep -Pzo '(?s)regular expression' fileName`  
功能如上  
-z 換行字元也會列入比較  
-P Perl 的樣式比對修正符  
注意!不是所有版本都有 -P 選項

### 特殊正規表示式

`[:print:]`  
可顯示字元 A-Z a-z 0-9 等等，不包含控制字元

### Perl 正規表示式

`(?s)`  
意思為 . 特殊字元也會比對換行字元

`.*?`  
比對盡可能少的字元

### 例如

`$ ps aux | grep apache2`  
顯示系統上運行程序的資訊並過濾只包含 apache2

`$ grep div /index.html`  
過濾 index.html 只包含 div 關鍵字

`$ grep -i -r ./ -e 'keyword'`  
不區分大小寫的遞迴搜尋當前目錄下 keyword 字串

`$ echo 'a,b,c,d,e' | grep -Po '.*?,'`  
輸出如下  
a,  
b,  
c,  
d,

`$ echo 'a,b,c,d,e' | grep -Po '.*,'`   
輸出如下  
a,b,c,d,

## locate

`$ locate keyword`

keyword 關鍵字

搜尋檔案  
該指令會搜尋整個檔案系統、定位關鍵字

檔案會被建立在資料庫，一天更新一次，所以剛建立的檔案可能會搜尋不到

## whereis

`$ whereis binaryFileName`

binaryFileName 二進位檔

搜尋二進位檔和操作手冊

## which

`$ which binaryFileName`

binaryFileName 二進位檔 

搜尋二進位檔

只搜尋 PATH 變數中的二進位檔

