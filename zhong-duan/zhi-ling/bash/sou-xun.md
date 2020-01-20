# 搜尋

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

## find

`$ find directory options expression`

directory 目錄  
options 選項  
expression 表達式

進階搜尋

指定搜尋的起點目錄，檔案名稱、  
建立或修改日期、擁有者、群組、權限、大小等

## grep

`grep keyword`

過濾輸出或者檔案內容

### 例如

`ps aux | grep apache2`  
顯示系統上運行程序的資訊並過濾只包含 apache2

`grep div /index.html`  
過濾 index.html 只包含 div 關鍵字

