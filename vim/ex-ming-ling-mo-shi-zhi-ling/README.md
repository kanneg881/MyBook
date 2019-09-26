# Ex命令模式指令

## 編輯命令

刪除一行  
`<Ctrl-u>`

刪除游標前面單字  
`<Ctrl-w>`

分割命令，你可以在一行里輸入多個命令。  
如果你想在參數里使用 `|` ，應該在前面加上 `\`   
注意：有些命令 \| 被當作參數，後面不能接命令  
詳情可以在 `:h :bar` 找到  
`|`

## 編輯文件

`:[range]co[py] {address}`  
把 `[range]` 指定的行複製到 `{address}` 表示的行之下

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

## 設定變數

設定變數 i 等於 0  
`:let i = 0`  
  
設定變數 i 等於 i + 1  
`:let i += 1`  


## 設定功能

暫時禁用高亮顯示搜尋匹配  
直到執行新的或重複搜尋命令為止  
`:nohlsearch`

## 特殊符號

當前文件名  
`%`

## 暫存器

顯示暫存器清單  
`:reg`  
  
顯示指定暫存器  
`:reg {register}`   
  
貼上暫存器內容到游標下方  
`:put {register}` 

## Quickfix

`:cnext`  
跳轉到下一項

`:cprev`  
跳轉到上一項

`:cfirst`  
跳轉到第一項

`:clast`  
跳轉到最後一項

`:cnfile`  
跳轉到下一個文件中的第一項

`:cpfile`  
跳轉到上一個文件中的最後一項

`:cc N`  
跳轉到第 N 項

`:copen`  
打開 quickfix 視窗

`:cclose`  
關閉 quickfix 視窗

`:cdo {cmd}`  
在 quickfix 列表中的每一行執行 `{cmd}`

`:cfdo[!] {cmd}`  
在 quickfix 列表的每個文件上執行 `{cmd}`  
工作方式相當於：

```text
:cfirst
:{cmd}
:cnfile
:{cmd}
```

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

## tags

`:tags {keyword}`  
跳到第一個匹配 `{keyword}` 的標籤處

`:tjump {keyword}`  
如果標籤匹配到多處，則跳到指定匹配 {keyword} 標籤處  
如果只有一處，直接跳到那處

`:tag`  
正向遍歷標籤歷史

`:pop`  
反向遍歷標籤歷史

`:tselect`  
調用標籤匹配列表

`:tnext`  
跳到下一個匹配的標籤

`:tprev`  
跳到上一個匹配的標籤

`:tfirst`  
跳到第一個匹配的標籤

`:tlast`  
跳到最後一個匹配的標籤

