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

`$ awk ' /regular/ {command}'`

同上，不過 // 之間為正規表達式  
只要符合就執行 command

### sed

`$ sed s/keyword/replace/g path/to/file > path/to/newFile`  
尋找位於 path/to/file 檔案的 keyword 內容並取代成 replace  
然後另存為  path/to/newFile  
keyword 為正規表示式  
s/keyword/replace/g 的 s 為取代  
s/keyword/replace/g 的 g 為全域搜尋  
如果沒有 g 則只取代搜尋到的第一個  
如果 g 改成數字 n，則指定取代搜尋到的第 n 個

`$ sed -i 's/\\/\//g fileName.txt`  
把 fileName.txt 的所有 \ 取代成 /  
因為 \ 是特殊字元，所以要加 \ 轉逸  
變成 \\，而 / 也是特殊字元，也需要轉逸  
所以這行指令 keyword 就是 \\  
replace 就是 \/  
-i 代表會把結果寫回輸入的檔案 fileName.txt 裡

### tr

`$ tr '\\-' '/|' < inputFile.txt > outputFile.txt`  
將 inputFile.txt 的 \ 取代成 /，- 取代成 \|  
並將結果輸出到 outputFile.txt  
因為 \ 是特殊字元，需要加上 \ 轉逸  
上述第1個 ' ' 的內容為要被取代的字元  
第2個 ' ' 的內容為要取代成裡面的字元  
所以 \\ 取代成 /  
- 取代成 \|

## 複製檔案

`$ cp [-p] file path/to/copyFile`  
複製一份 file 命名為 copyFile 到指定目錄  
不指定目錄就是在當前目錄  
不指定檔案名稱就是原檔名  
不能都不指定  
-p 保留檔案本身的存取模式、所有權、時間戳記

## 合併檔案

`$ join -1 2 -2 1 -t, students.txt grades.txt`  
合併檔案 students.txt 和 grades.txt  
-1 2 代表指定第1個檔案的第2個欄位  
-2 1 代表指定第2個檔案的第1個欄位  
用此兩個欄位將資料合併  
-t, 代表用 , 做區隔

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

合併後

1,student1,80  
2,student2,90  
3,student3,100

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

