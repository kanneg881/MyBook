# 基礎

`((a=b+1))`  
如果是純數值計算，可以用兩個括號來計算  
因為是純數值的關係，所以不需要在變數前加上 $ 符號  
來表示「引用變數值」

`${variable}`  
${} 大括號裡面可以對變數 variable 進行操作

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
如果要取出所有不重複的索引鍵值  
使用 `${!variable[@]}`

`variable[$key]++`  
遞增  
$key 陣列索引

### 陣列

`declare -a variable`  
宣告名為 variable 的陣列  
索引為數字

### 數值

`declare -i variable`  
宣告名為 variable 的數值變數

