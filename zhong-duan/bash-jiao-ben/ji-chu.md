# 基礎

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

## 關聯陣列

`declare -A variable`  
宣告名為 variable 的關聯式陣列  
注意!這需要 bash 4.0 以後的版本才支援

關聯式陣列的索引可以是字串或數字  
如果要取出所有不重複的索引鍵值  
使用 `${!variable[@]}`

`variable[$key]++`  
遞增  
$key 陣列索引

