# Ex命令模式指令

## 自動補全

`<Ctrl-d>`  
顯示自動補全列表

`<Tab>`  
正向遍歷自動補全列表

`<Shift-Tab>`  
反向遍歷自動補全列表

`<Ctrl-r><Ctrl-w>`  
複製游標下的單詞到命令行中

`<Ctrl-r><Ctrl-a>`  
複製游標下的字串到命令行中

`<Up>` 和 `<Down>`  
切換到命令行模式 `:`  
再按 `<Up>` 或 `<Down>` 回溯歷史命令

## 編輯命令

`|`  
分割命令，你可以在一行里輸入多個命令。  
如果你想在參數里使用 `|` ，應該在前面加上 `\`   
注意：有些命令 \| 被當作參數，後面不能接命令  
詳情可以在 `:h :bar` 找到

## 編輯文件

`:pw[d]`  
顯示當前目錄

`:cd[!] {path}`  
切換當前目錄為 `{path}`

`:[range]co[py] {address}`  
把 `[range]` 指定的行複製到 `{address}` 表示的行之下

`:[range]m[ove] {address}`  
把 `[range]` 指定的行移動到 `{address}` 表示的行之下

`[range]j[oin][!] [flags]`  
連接 `[range]` 範圍的行

`:t`  
和 `:copy` 等價

`:[range]y[ank] [x]`  
抽出 `[range]` 所指定的行到暫存器 `[x]`

`:[range]d[elete] [x]`  
刪除 `[range]` 範圍的行 \(缺省: 當前行\) \[到暫存器 x 裡\]

`:w [path/file]`  
存檔，可以加路徑和檔案名稱，沒加就是覆蓋當前檔案

`:wa[ll]`  
保存所有已修改的緩衝區。沒有文件名的緩衝區會報錯。  
只讀的緩衝區不會被寫入。

`:[range]up[date][!] [++opt] [>>] [file]`  
和 `:write` 類似，但只有在某些已修改的時候才寫

`:q[uit]`  
退出當前視窗。如果是最後的一個，退出 Vim。

`:[range]sor[t][!] [b][f][i][n][o][r][u][x] [/{pattern}/]`  
給 `[range]` 裡的行排序。如果沒有指定行範圍，給所有行排序。

`:[range]> [flags]`  
將 `[range]` 指定的行右移 'shiftwidth' 列  
多個 '&gt;' 右移 多個 'shiftwidth' 列

## 查看

`:files[!] [flags]  
:buffers[!] [flags]  
:ls[!] [flags]`  
顯示所有緩衝區

`[!]`   
包括列表外緩衝區

## 設定變數

設定變數 i 等於 0  
`:let i = 0`  
  
設定變數 i 等於 i + 1  
`:let i += 1`

## 特殊符號

當前文件名  
`%`

## 暫存器

`:reg`  
顯示暫存器清單

`:reg {register}`  
顯示指定暫存器  
  
`:[line]pu[t] [x]`  
放置文本 \[從寄存器 x\] 在行號 \[line\] \(缺省為當前行\) 之後

## shell

`:!{cmd}`  
在 vim 執行 shell 命令

`:shell`  
開啟 shell 互動式窗  
`exit` 命令離開 shell 返回 vim

## :global

`:[range]g[lobal]/{pattern}/[cmd]`  
在 `[range]` （缺省是 `%` 作用整個文件）界定的匹配模式  
`{pattern}` 的文本行上執行 Ex 命令 `[cmd]` \(缺省是 `:p` \)  
`[cmd]` 前面可以接受 `[range]`

`:[range]g[lobal]!/{pattern}/[cmd]`  
在 `[range]` （缺省是 `%` 作用整個文件）界定的不匹配模式  
`{pattern}` 的文本行上執行 Ex 命令 `[cmd]` \(缺省是 `:p` \)

`:[range]v[global]/{pattern}/[cmd]`  
等同於 `:g!`

## :normal

`:{range}norm[al][!] {commands}`   
在 `{range}` 指定的範圍中的每行執行若干普通模式命令 `{commands}`

## :source

`:so[urce] {file}`  
從 {file} 裡讀取Ex命令，即“：”開頭的命令，並執行。  
{file} 通常是 \*.vim 檔

## 參數列表

`:args`  
顯示參數列表

`:rew[ind] [++opt] [+cmd]`  
開始編輯參數列表的第一個文件

`:first`  
:rewind 的別名

`:[count]n[ext] [++opt] [+cmd]`  
編輯向後第 `[count]` 個文件

`:[range]argdo[!] {cmd}`  
對參數列表裡的每個文件執行 `{cmd}`

