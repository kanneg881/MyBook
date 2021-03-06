# 基礎

`((a=b+1))`  
如果是純數值計算，可以用兩個括號來計算  
因為是純數值的關係，所以不需要在變數前加上 $ 符號  
來表示「引用變數值」

`${variable}`  
${} 大括號裡面可以對變數 variable 進行操作

`${#variable}`  
取得變數 variable 字元數量

`${variable:from:length}`  
取得變數 variable 從 from 開始 length 個字元  
例如：`${variable:0:1}`  
variable 從第0個起取1個字元

`$(command)`  
command 在 subshell 執行  
並且可以把回傳值賦予變數中  
例如：  
`VAR=$(ls)`

## 預設值

`VAR=${1:- default value}`  
假設預設值 $1 參數不存在  
則 VAR=default value

## 宣告

### 關聯陣列

`declare -A variable`  
宣告名為 variable 的關聯式陣列  
注意!這需要 bash 4.0 以後的版本才支援

關聯式陣列的索引可以是字串或數字

`${variable[@]}`  
取出所有陣列元素

`${!variable[@]}`  
取出所有不重複的索引鍵值

`${#variable[@]}`  
取得陣列長度

`${variable[*]}`  
一次取出陣列所有元素  
用空白間隔，當作一個字串

`variable[$key]++`  
遞增  
$key 陣列索引

### 陣列

`declare -a variable`  
宣告名為 variable 的陣列  
索引為數字

`arrayVariable=( ${variable} )`  
使用括號，將變數轉變成陣列  
例如：  
'1 2 3 4 5' 字串會轉變為  
\[1, 2, 3, 4, 5\] 陣列

`arrayVariable+=( "$variable" )`   
將變數字串附加到陣列裡

### 數值

`declare -i variable`  
宣告名為 variable 的數值變數

## 暫時的變數

`variable=$a command`  
variable 被賦予變數 a 的值，立即接 command 指令  
variable 只有在 command 指令執行時有效  
command 指令結束後，variable 就變回原本的值

