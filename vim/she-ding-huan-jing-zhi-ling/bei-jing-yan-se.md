# 編輯器高亮顏色

## 介紹

編輯器高亮的顏色，都可以透過設定去修改  
包括游標所在行的背景顏色都可

## 常用指令

`colo[rscheme]`  
輸出當前激活的色彩方案名

`colorscheme {name}`  
載入色彩方案 {name}  
若不知道要設定哪個  
可以在輸入完 colorscheme \(空白\)後按 `<Ctrl-d>`  
顯示列表  
作者是使用[Dracula](../wai-gua-tui-jian/wai-guan/dracula.md)

`hi[ghlight]`  
列出當前所有的有屬性設定的高亮組

`hi[ghlight] {group-name}`  
列出一個高亮組

`hi[ghlight] clear`  
重置高亮設定為預設值

## 高亮組

`hi[ghlight] [default] {group-name} {key}={arg} ..`  
增加高亮組，或者更改現有的組高亮設定

\[default\] 可以設定組的預設高亮。如果該組已經設定了高亮  
或者已經存在鏈接，忽略該命令

{group-name} 組名，例如 Cursor 就是游標所在的字元  
這樣就算一組  
更多的組名的名稱可以查詢 vim help  
`:h highlight-groups`

{key} 請參考底下的[說明](bei-jing-yan-se.md#key)

### 使用範例

highlight Cursor guibg=red  
高亮游標所在位置的背景顏色為紅色

## key 和 arg

### 編輯器環境

主要有三種

term 普通的終端 \(vt100、xterm\)

cterm 色彩終端 \(MS-DOS 控制台、color-xterm  
帶有 "Co" termcap 項目的終端\)

gui 圖形使用者介面

### 範例

假設我要修改 cterm 的顏色

ctermfg={color-nr}  
修改 cterm 前景顏色

ctermbg={color-nr}  
修改 cterm 背景顏色

上面指令左邊為 key 右邊為 arg

{color-nr} 為顏色  
可以用顏色名 white black ...  
如果在圖形使用者介面可以用顏色編碼 \#ffffff

arg 不只可以設定顏色  
還有其他的像是讓字體變粗體等等

查詢 vim help 看更多  
`:help highlight-args`  








