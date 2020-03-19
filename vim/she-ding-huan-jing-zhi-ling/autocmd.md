# autocmd

當觸發某些條件時，自動執行設定的指令

`:au[tocmd] [group] {event} {pat} [nested] {cmd}`  
把 {cmd} 加到 Vim 在匹配 {pat} 模式的文件執行 {event} 事件時自動執行的命令列表  
{event} 事件  
{pat} 模式  
{cmd} 指令

例如：  
`:autocmd BufRead */doc/*.txt set tw=78`  
設定 txt 檔最大寬度

## event

事件為觸發的條件

`:h event`  
使用幫助文件查看事件名稱

## pat

模式為匹配文件的模式

例如  
\* 匹配所有文件  
\*.txt 匹配副檔名為 txt 文件  
/path/to/\*.c 匹配資料夾路徑下所有的 c 語言檔

## cmd

執行的指令

例如：  
`setlocal ru`



