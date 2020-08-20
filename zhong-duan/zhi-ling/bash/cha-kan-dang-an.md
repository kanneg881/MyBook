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

## 排序

### sort

`$ sort [-f][-k][-n][-o][-r][-t] fileName.txt`  
將檔案做排序  
-f 忽略大小寫  
-k 使用行中的一部份資料做排序，欄位以空白區隔  
  
-n 使用數字排序  
否則會使用字元排序  
例如：10 會在 2 之前  
  
-o 將輸出寫至檔案  
-r 以降冪排序  
-t 指定區隔字元

#### 舉例

使用以下檔案做示範

{% code title="fileName.txt" %}
```text
2020/08/21 10:30 Friday
2019/06/01 09:09 Saturday
```
{% endcode %}

`$ sort -k 2 fileName.txt`  
使用第2個欄位做排序  
結果：  
2019/06/01 09:09 Saturday  
2020/08/21 10:30 Friday

`$ sort -k 1.6,1.7 fileName.txt`   
使用第1個欄位的第6 ~ 7 的字元做排序  
也就是月份的 08 和 06  
結果：  
2019/06/01 09:09 Saturday  
2020/08/21 10:30 Friday

