# Ex命令模式指令

## 快捷鍵

`<Ctrl-b>`  
移動到命令開頭

`<Ctrl-d>`  
顯示可輸入的命令清單  
當讀者輸入指令前幾個字元後  
可以顯示有哪些指令可以輸入  
例如：  
`:ec<Ctrl-d>`  
可以看到其中有一個是 echo

`<Ctrl-e>`  
移動到命令結尾

`<Ctrl-f>`  
打開可編輯的命令列視窗  
其中顯示的是之前執行過的命令的歷史紀錄  
按 &lt;Enter&gt; 執行游標所在的那一行  
按 &lt;Ctrl-c&gt; 回到命令列並寫入游標的內容  
`:help cmdline-editing` 查看更多命令行編輯

`<Ctrl-Left>` 或 `<Shift-Left>`  
向左移動一個單字

`<Ctrl-n>` 或 `<Down>`  
瀏覽下個命令的歷史紀錄

`<Ctrl-p>` 或 `<Up>`  
瀏覽上個命令的歷史紀錄

`<Ctrl-Right>` 或 `<Shift-Right>`  
向右移動一個單字

## 幫助

`:h[elp]`  
打開一個窗口並以只讀方式顯示幫助文件

`:h[elp] {subject}`  
類似於 `:help`，但附加跳轉到 `{subject}` 標籤上

例如  
`:help :h`  
打開幫助文件查看幫助指令

## 編輯命令

`|`  
分割命令，你可以在一行里輸入多個命令。  
如果你想在參數里使用 `|` ，應該在前面加上 `\`   
注意：有些命令 \| 被當作參數，後面不能接命令  
詳情可以在 `:h :bar` 找到

## 編輯文件

`:cd[!] {path}`  
切換當前目錄為 `{path}`

`:[range]co[py] {address}`  
把 `[range]` 指定的行複製到 `{address}` 表示的行之下

`:[range]d[elete] [x]`  
刪除 `[range]` 範圍的行 \(缺省: 當前行\) \[到暫存器 x 裡\]

`:e[dit] [++opt] [+cmd] {file}`  
編輯文件 `{file}`

`:[range]j[oin][!] [flags]`  
連接 `[range]` 範圍的行

`:lc[d][!] {path}`  
和 `:cd` 類似，但只設置當前窗口的當前目錄  
別的窗口的當前目錄保持不變

`:[range]m[ove] {address}`  
把 `[range]` 指定的行移動到 `{address}` 表示的行之下

`:pw[d]`  
顯示當前目錄

`:[range]ret[ab][!] [new_tabstop]`  
把所有包含 &lt;Tab&gt; 的空白序列替代成由新的製表位  
\[new\_tabstop\] 確定的空白序列。如果你不指定新的製表位，  
或者它為 0，Vim 使用原來的製表位 tabstop

`:[range]sor[t][!] [b][f][i][n][o][r][u][x] [/{pattern}/]`  
給 `[range]` 裡的行排序。如果沒有指定行範圍，給所有行排序。

`:t`  
和 `:copy` 等價

`:[range]up[date][!] [++opt] [>>] [file]`  
和 `:write` 類似，但只有在某些已修改的時候才寫

`:wa[ll]`  
保存所有已修改的緩衝區。沒有文件名的緩衝區會報錯。  
只讀的緩衝區不會被寫入。

`:w[rite] [++opt]`  
將整個緩衝區寫入當前文件

`:w fileName`  
寫入到 fileName 裡面  
fileName 檔案名稱

`:[range]y[ank] [x]`  
抽出 `[range]` 所指定的行到暫存器 `[x]`

`:[range]> [flags]`  
將 `[range]` 指定的行右移 'shiftwidth' 列  
多個 '&gt;' 右移 多個 'shiftwidth' 列

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

`:reg[isters] {arg}`  
顯示 {arg} 裡提到的編號和命名暫存器的內容  
例如:  
`:reg 1a`  
顯示暫存器 '1' 和 'a'  
{arg} 裡可以用空格  
  
`:[line]pu[t] [x]`  
放置文本 \[從寄存器 x\] 在行號 \[line\] \(缺省為當前行\) 之後

## shell

`:!{cmd}`  
在 vim 執行 shell 命令

`:shell`  
開啟 shell 互動式窗  
`exit` 命令離開 shell 返回 vim

`:[range]r[ead] [++opt] !{cmd}`  
執行 `{cmd}` 並把它的標準輸出插入到遊標下方

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

`:ar[gs]`  
顯示參數列表，當前文件以方括號表示

`:ar[gs] [++opt] [+cmd] {arglist}`  
定義{arglist}為新的參數列表並編輯其中的第一個

`:rew[ind] [++opt] [+cmd]`  
開始編輯參數列表的第一個文件

`:first`  
:rewind 的別名

`:[count]n[ext] [++opt] [+cmd]`  
編輯向後第 `[count]` 個文件

`:[range]argdo[!] {cmd}`  
對參數列表裡的每個文件執行 `{cmd}`

## 跳轉

`:+N`  
向下移動 N 行

`:-N`  
向上移動 N 行

`:N`  
移動到第 N 行

`:jumps`  
查看跳轉列表

## 改變列表

`:changes`  
查看改變列表

