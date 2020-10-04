# 建立與修改檔案或目錄

## 檔案

### awk

`$ awk '$1 == "string" {command}' fileName`  
awk 會迭代 fileName 的每一行內容  
迭代的每一行如果第一個字是 string 就執行 command 指令  
$0 代表整行  
$1 第1個字  
$2 第2個字  
以此類推  
預設是以空格來區隔每個字

`$ awk '$1 ~ "string" {command}' fileName`   
同上  
~ 代表是否匹配字串 "string"

`$ awk ' /regular/ {command}'`  
同上，不過 // 之間為正規表達式  
只要符合就執行 command

`$ awk -F "," '{command}' fileName`  
同上，迭代 fileName 的每一行內容  
-F 指定分隔符號，這裡為 ,

`$ awk '  
{command}  
END {command}' fileName`  
當 awk 迭代 fileName 的每一行內容後  
最後再執行 END 裡面的 command

`$ awk '{print NF}' fileName`  
輸出每一行的欄位數  
NF 欄位數

`gsub(search, replace, variable)`  
awk command 的函式  
將變數 variable 中出現 search 字樣取代成 replace

### sed

`$ sed 's/keyword/replace/g' path/to/file > path/to/newFile`  
尋找位於 path/to/file 檔案的 keyword 內容並取代成 replace  
然後另存為  path/to/newFile  
keyword 為正規表示式  
s/keyword/replace/g 的 s 為取代  
s/keyword/replace/g 的 g 為全域搜尋  
如果沒有 g 則只取代搜尋到的第一個  
如果 g 改成數字 n，則指定取代搜尋到的第 n 個

`$ sed -i 's/\\/\//g' fileName.txt`  
把 fileName.txt 的所有 \ 取代成 /  
因為 \ 是特殊字元，所以要加 \ 轉逸  
變成 \\，而 / 也是特殊字元，也需要轉逸  
所以這行指令 keyword 就是 \\  
replace 就是 \/  
-i 代表會把結果寫回輸入的檔案 fileName.txt 裡

`$ sed -i '_bk' 's/\\/\//g' fileName.txt`  
如果是 mac os 系統，需要加上後綴字做備份  
Linux 使用如上的指令即可  
此指令和上一個一樣，但會把原始檔備份到 fileName.txt\_bk  
'\_bk' 代表備份檔的後綴字  
不想要備份檔可以在 -i 後輸入 ''  
`$ sed -i '' 's/\\/\//g' fileName.txt`

`$ sed -e 's/keyword/replace/' -e 's/keyword/replace/'`  
-e 連接多個 sed 指令

### tr

`$ tr '\\-' '/|' < inputFile.txt > outputFile.txt`  
將 inputFile.txt 的 \ 取代成 /，- 取代成 \|  
並將結果輸出到 outputFile.txt  
因為 \ 是特殊字元，需要加上 \ 轉逸  
上述第1個 ' ' 的內容為要被取代的字元  
第2個 ' ' 的內容為要取代成裡面的字元  
所以 \\ 取代成 /  
- 取代成 \|

`$ tr -d '\r' < inputFile.txt > outputFile.txt`   
將 inputFile.txt 的 \r 字元刪除  
並將結果輸出到 outputFile.txt  
-d 為指定要刪除的字元

## 複製檔案

`$ cp [-p] file path/to/copyFile`  
複製一份 file 命名為 copyFile 到指定目錄  
不指定目錄就是在當前目錄  
不指定檔案名稱就是原檔名  
不能都不指定  
-p 保留檔案本身的存取模式、所有權、時間戳記

## 排序

### sort

`$ sort [-f][-k][-n][-o][-r][-t][-u] fileName.txt`  
將檔案做排序  
-f 忽略大小寫  
-k 使用行中的一部份資料做排序，欄位以空白區隔  
  
-n 使用數字排序  
否則會使用字元排序  
例如：10 會在 2 之前  
  
-o 將輸出寫至檔案  
-r 以降冪排序  
-t 指定區隔字元  
-u 清除重複的內容

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

## 消除重複

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

## 合併檔案

{% tabs %}
{% tab title="students.txt" %}
```text
student1,1
student2,2
student3,3
```
{% endtab %}

{% tab title="grades.txt" %}
```
1,80
2,90
3,100
```
{% endtab %}
{% endtabs %}

檔案範例

`$ join -1 2 -2 1 -t, students.txt grades.txt`  
合併檔案 students.txt 和 grades.txt  
-1 2 代表指定第1個檔案的第2個欄位  
-2 1 代表指定第2個檔案的第1個欄位  
用此兩個欄位將資料合併  
-t, 代表用 , 做區隔

合併後

1,student1,80  
2,student2,90  
3,student3,100

{% tabs %}
{% tab title="newFilePath.txt" %}
```text
a.txt
b.txt
c.txt
d.txt
```
{% endtab %}

{% tab title="oldFilePath.txt" %}
```
1 a.txt
2 b.txt
3 c.txt
```
{% endtab %}
{% endtabs %}

`$ join -1 1 -2 2 -a 1 newFilePath.txt oldFilePath.txt`  
合併檔案 newFilePath.txt 和 oldFilePath.txt  
-1 1 代表指定第1個檔案的第1個欄位  
-2 2 代表指定第2個檔案的第2個欄位  
用此兩個欄位將資料合併  
-a 1 代表顯示第一個檔案中，比對不符合的欄位

合併後

a.txt 1  
b.txt 2  
c.txt 3  
d.txt

d.txt 代表不符合的檔案

## 移動或重新命名檔案

`$ mv file newFile`  
重新命名 file 為 newFile  
mv 是搬移指令，搬移目錄或檔案  
用這個方法來重新命名

## 移除檔案

`$ rm file`  
移除檔案

## 建立檔案

`$ touch fileName`  
建立新檔

`$ mktemp`  
建立暫存的檔案  
一般會存在暫存區  
暫存區的檔案過一段時間後會自動清除

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

