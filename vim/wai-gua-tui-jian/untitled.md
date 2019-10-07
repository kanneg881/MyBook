# NERD Comment

## 介紹

快速註解程式碼

## 下載

[https://github.com/scrooloose/nerdcommenter](https://github.com/scrooloose/nerdcommenter)

## 簡易說明

`[count]<leader>cc`  
在可視模式下註解

`[count]<leader>c<space>`  
切換註解

`[count]<leader>cm`  
使用一組多行註解的方式

`[count]<leader>cs`  
漂亮格式的註解

`<leader>c$`  
當前游標位置到結尾註解

`<leader>cA`  
附加註解到行末，並切換插入模式

`<leader>ca`  
切換註解符號

`[count]<leader>cl`  
對齊左側註解

`[count]<leader>cu`  
關閉註解

### 配置 .vimrc

```text
" 註解後面多一個空白
let g:NERDSpaceDelims = 1
```

