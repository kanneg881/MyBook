# 參數

## $

要在指令稿使用參數需要使用特殊符號來取用

$\# 參數數量  
$0 指令稿本身  
$1 第一個參數  
$2 第二個參數  
...以此類推

例如  
./file.sh a b c

$\# 為 3  
$0 為 ./file.sh  
$1 為 a  
$2 為 b  
$3 為 c

$? 前一指令傳回的值

$$ 程序的識別碼

$! 上一個在背景執行的腳本的程序的識別碼

## %

% 代表腳本 job 編號  
%1 %2 %3 代表放到背景端的順序

## 清除參數

`shift number`  
清除 number 個參數，後面會依序替補  
number 數字

### 例如

`shift 3`  
清除3個參數，$4 會替補成 $1，$5 會替補成 $2

`shift $((var))`  
清除 var 變數個參數

## 檔案描述符

`command 4< path/to/file 5< path/to/file`  
從檔案描述符4和5讀取內容  
腳本可以指定檔案描述符取得內容

### 例如

```text
while true
do
    read line1 <&4
    read line2 <&5
done 4< ${file1} 5< ${file2}
```

