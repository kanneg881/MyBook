# 基礎

`${variable}`  
${} 大括號裡面可以對變數 variable 進行操作

$\(command\)  
command 在 subshell 執行  
並且可以把回傳值賦予變數中  
例如：  
`VAR=$(ls)`

## 預設值

`VAR=${1:- default value}`  
假設預設值 $1 參數不存在  
則 VAR=default value

