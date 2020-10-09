# 查看檔案

## base64

`$ base64 [-d] fileName`  
把檔案編碼成 base64 編碼  
fileName 檔案名稱  
-d 解碼 base64

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

`$ cut -c22- fileName`  
從字元位置 22 起開始保留到結尾\(-\)

`$ cut -f1-3 fileName`  
指定擷取第1到3的欄位

`$ cut -f1,3 fileName`  
指定擷取第1和3的欄位

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

## sdiff

`$ sdiff [-i][-s][-w] file1 file2`  
比對 file1 和 file2 檔案內容差異

-i 不區分大小寫  
-s 不輸出相同行數  
-w 輸出每一行字元數上限

### 舉例

`$ sdiff -i -s -w100 file1 file2`

`$ cat file1 | sdiff - file2`  
- 代表比對標準輸入的內容

## sha1sum

`$ sha1sum [-c][--quiet] fileName`  
輸出 fileName 的訊息摘要  
也就是此檔案的雜湊值  
-c 檢查 fileName 已經產生雜湊訊息的檔案路徑內容  
--quiet 只輸出比對失敗的檔案

## tail

`$ tail -f path/to/file`  
持續讀取檔案  
並在新增資料行時立即顯示到標準輸出

`$ tail -f path/to/file | command`  
同上，並進一步管線到其他指令

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

`$ tail --pid=$$ path/to/file`  
--pid 追蹤上游的程序  
$$ 腳本的程序識別碼  
path/to/file 檔案位置

## uniq

`$ uniq [-c][-f Number][-i] fileName.txt`  
消除重複的行數，需要先做排序  
-c 印出重複的次數  
-f 忽略前 Number 個欄位，預設以空格做排序  
-i 忽略大小寫

### 範例

{% tabs %}
{% tab title="fileName.txt" %}
```text
2020/08/21 10:30 Friday
2019/06/01 09:09 Saturday
2019/06/01 09:09 Saturday
```
{% endtab %}

{% tab title="fileName2.txt" %}
```
2020/08/21 10:30 Friday
2019/06/01 09:09 Saturday
2019/06/02 09:09 Saturday
```
{% endtab %}
{% endtabs %}

`$ uniq -c fileName.txt`  
排序並印出重複次數  
結果：  
1 2020/08/21 10:30 Friday  
2 2019/06/01 09:09 Saturday

`$ uniq -c -f 1 fileName.txt`  
忽略前1個欄位後做排序，並印出重複次數  
結果：  
1 2020/08/21 10:30 Friday  
2 2019/06/01 09:09 Saturday

## wc

`$ wc [-l]`  
顯示行數、字數和字節數  
-l 只顯示行數

## xxd

`$ xxd [-b][-l][r][-s]`  
以二進制或十六進制顯示檔案內容  
-b 以二進制顯示，預設為十六進制  
-l 指定印出位元組長度  
-r 十六進制轉 ASCII 碼  
-s 指定從第 n 個位元組開始輸出

### 舉例

`$ xxd -s 5 -l 10 fileName`   
以十六進制輸出 fileName 檔案內容  
從第5個位元組開始，印出10個位元組



