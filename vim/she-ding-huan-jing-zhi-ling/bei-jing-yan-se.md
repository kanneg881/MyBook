# 背景顏色

## 介紹

編輯器的顏色，都可以透過設定去修改  
包括游標所在行的背景顏色都可

## 說明

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

`hi[ghlight] [default] {group-name} {key}={arg} ..`  
增加高亮組，或者更改現有的組高亮設定  
{key} 請參考底下的[說明](bei-jing-yan-se.md#key)  
用 \[default\] 參數可以設定組的預設高亮。如果該組已經設定了高亮  
或者已經存在鏈接，忽略該命令

## key

### 主要有三種

term 普通的終端 \(vt100、xterm\)

cterm 色彩終端 \(MS-DOS 控制台、color-xterm  
帶有 "Co" termcap 項目的終端\)

gui GUI

### 範例

ctermfg={color-nr}  
修改 cterm前景顏色

ctermbg={color-nr}  
修改 cterm背景顏色







