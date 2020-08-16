# 查看檔案

## cat

`$ cat fileName`  
顯示檔案

`$ cat > fileName`  
建立檔案，之前的內容會覆蓋  
輸入完內容按 `<Ctrl-D>` 回到終端

`$ cat >> fileName`  
建立檔案，內容添加在原檔案後方  
輸入完內容按 `<Ctrl-D>` 回到終端cut

## cut

`$ cut [-c][-d][-f] fileName`  
每一行按照分隔符號剖析文字  
-c 指定擷取的字元位置，預設為 1  
-d 指定分隔符號字元，預設為 tab  
-f 指定擷取的欄位位置，預設為 1  
ex :  
`$ cut -d' ' -f3 fileName`  
指定擷取欄位為第3個，並以空格為分隔符號  
`$ cut -c22-`  
從字元位置 22 起開始保留到結尾\(-\)

## file

`$ file [-f][-k][-z] fileName`  
識別檔案類型，尤其對沒有副檔名或錯誤的副檔名特別好用  
-f 讀取檔案清單以便分析給定檔案  
-k 不要停在第一個比對符合項目;要把所有符合類型的檔案都列出來  
-z 檢視壓縮黨內部

## head

`$ head [-c][-number] path/to/file`  
顯示檔案開頭 10 行  
-c 指定要輸出多少位元組  
-number 指定行數，例如 -20  
path/to/file 檔案位置

## less

`$ less path/to/file`  
查看檔案內容  
按 `/` 可以搜尋關鍵字  
按 `n` 跳下一個  
英文有一句諺語 : less is more   
應對了  less 和 more 指令

## more

`$ more path/to/file`  
查看檔案內容  
按 `<Enter>` 顯示下一行  
按 `q` 離開

## nl

`$ nl [option] path/to/file`  
顯示檔案內容，並顯示行號  
-ba 行數包含空白，預設不包含

## sort

`$ sort [-n][-r]`  
將資料排序，可以用 \| 管線傳遞  
-n 依照數字風格排序  
-r 由大到小排序

## tail

`$ tail [-number] path/to/file`  
顯示檔案尾部 10 行  
-number 指定行數，例如 -20  
path/to/file 檔案位置

`$ tail -n +2 path/to/file`  
從第2行開始顯示檔案  
-n +2 指定由上往下第幾行開始  
path/to/file 檔案位置  
也可以重新導向到這裡  
例如：  
`$ cat path/to/file | tail -n +2` 

