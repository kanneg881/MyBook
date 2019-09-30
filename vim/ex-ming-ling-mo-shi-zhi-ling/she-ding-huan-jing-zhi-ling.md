# 設定環境指令

`:set hidden`  
如果想保留修改了的緩衝區但不寫回，打開 'hidden' 選項

`:set hlsearch`  
高亮顯示搜尋匹配

`:set ignorecase`  
是否不區分大小寫

`:set nohlsearch`  
禁用高亮顯示搜尋匹配

`:set spell`  
開啟拼寫檢查

`:set spellfile`  
可以指定拼寫文件的路徑  
`zg` 和 `zw` 保存和刪除的位子  
也可以指定多個

```text
setlocal spelling=~/.vim/spell/en.utf-8.add
setlocal spelling=~/mySpell/myWord.utf-8.add
```

`1zg` 代表存在 en.utf-8.add  
`2zg` 代表存在 myWord.utf-8.add

`:set spelllang`  
設定拼寫語言  
例如  
`:set spelllang=en_us,nl`  
設定為美式英語、荷蘭語

`:set smartcase`  
智能的大小寫敏感

`:set ts=number sts=number sw=number et`  
number 為數字  
ts tabstop 為 tab 空格數  
sts softtabstop 為符合 ts 空格是就變成 tab  
sw shiftwidth 為縮排所需的 Space 個數  
et exandtab 為插入空白

