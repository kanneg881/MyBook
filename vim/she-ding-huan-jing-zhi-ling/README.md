# 環境設定

## 介紹

vim 可以設定很多環境，通常都是寫在 [vimrc](../shen-me-shi-vimrc/)

大部分接可以直接在 [Ex命令模式](../ex-ming-ling-mo-shi-zhi-ling/)執行

例如  
`set number`  
在 Ex 命令就直接打  
`:set number`

## 環境指令

`colorscheme {name}`  
載入色彩方案 {name}  
若不知道要設定哪個  
可以在輸入完 colorscheme \(空白\)後按 `<Ctrl-d>`  
顯示列表  
作者是使用[Dracula](../wai-gua-tui-jian/wai-guan/dracula.md)

`filetype plugin indent on`  
檔案類型 檢測 插件 縮排 打開

`set autoindent`  
換行時自動縮進

`set backup`  
需要備份文件

`set cindent`  
使用 C/C++ 語言的自動縮排方式

`set cursorline`  
高亮光標所在的螢幕行

`set clipboard=unnamed`  
vim 剪貼板跟系統剪貼板共用  
例如 `yy` 複製一行，可以到外部貼上 `<command>V`  
外部複製的內容也可以在 vim 用 `p` 貼上

`set directory=$HOME/.vim/swap//`  
交換文件統一存放目錄 

`set encoding=utf8`  
設定檔案編碼，解決中文亂碼問題

`set expandtab`  
tab 以空格取代

`set filetype=myfiletype`  
如果檔案沒有識別或識別錯誤，可以手動設定 filetype

`set guifont=字型檔:h{Number}`  
gui 版 vim 字型  
{Number} 字型大小  
舉例：  
`set guifont=MesloLGL\ Nerd\ Font:h18`

`set  guioptions=egmrLtT`  
gui 版 vim 使用的部件和選項  
每一個字母都代表一個選項  
如果不想要某個選項把那個字母刪掉即可  
egmrLtT 是預設值  
主要可以設定滾動條顯示  
r 右邊的滾動條總是存在  
R 如有垂直分割的窗口，右邊的滾動條總是存在  
l 左邊的滾動條總是存在  
L 如有垂直分割的窗口，左邊的滾動條總是存在

`set hidden`  
如果想保留修改了的緩衝區但不寫回，打開 'hidden' 選項

`set history=[number]`  
歷史命令數量為 `[number]`

`set hlsearch`  
高亮顯示搜尋匹配

`set ignorecase`  
是否不區分大小寫

`set incsearch`  
輸入搜索命令時，顯示目前輸入的模式的匹配位置

`set linebreak`  
在某些字元才能自動摺行，避免斷句不乾淨

`set linespace={number}`  
設定每行的間距，高度的差距  
number 為距離  
舉例：  
`set linespace=2`

`set list`  
顯示 tab 尾部空白、換行符號  
不顯示則改成 nolist

`set nobackup`  
不需要備份文件

`set noswapfile`  
緩衝區不建立交換文件  
此為當檔案尚未存檔時，保留在相同目錄的暫存檔  
以免發生不可預期的事情而沒存檔

`set nowritebackup`  
編輯時不備份文件

`set number`  
顯示行號

`set nonumber`  
不顯示行號

`set ruler`  
顯示游標位置的行號和列號  
和在整個文件的比例

`set scrolloff=number`  
游標上下兩側最少保留的螢幕行數  
number 為數字

`set smartcase`  
智能的大小寫敏感

`set showcmd`  
在螢幕最後一行顯示（部分的）命令  
關閉則改成 noshowcmd

`set shortmess+=c`  
不顯示插入補全選單訊息

`set showtabline=number`  
本選項的 number 值指定何時顯示帶有標籤頁標籤的行:  
 0: 永遠不會  
1: 至少有兩個標籤頁時才會  
2: 永遠會

`set showmode`  
在插入，替換和可視模式裡，在最後一行提供消息  
關閉則改成 `noshowmode`

`set splitbelow`  
如果打開，視窗的分割會把新視窗放到當前視窗之下

`set splitright`  
如果打開，視窗的分割會把新視窗放到當前視窗之右

`set signcolumn=yes`  
是否繪製標誌列

`set transparency={number}`  
設定背景透明度 0-100  
此為 gui 版 vim 才有效  
0 為不透明  
100 為完全透明  
在桌面設定 50 看起來很像高科技...

`set ts=number sts=number sw=number et`  
number 為數字  
ts tabstop 為 tab 空格數  
sts softtabstop 把 &lt;Tab&gt; 算作空隔的數目  
sw shiftwidth 為縮排所需的 Space 個數  
et exandtab 為插入空白

`set updatetime=4000`  
如果過了這麼多毫秒數以後還沒有任何輸入，把交換文件寫入磁盤

`set wildmenu`  
產生自動補全的文件名菜單  
例如下列指令就會產生菜單  
`:e <Tab>`  
正向遍歷文件  
`:e <Shift-Tab>`  
反向遍歷文件

`set wrap`  
超出視窗寬度的文字行都會被迴繞顯示 

`syntax on`  
語法高亮

## 拼寫

`set spell`  
開啟拼寫檢查

`set spellfile`  
可以指定拼寫文件的路徑  
`zg` 和 `zw` 保存和刪除的位子  
也可以指定多個

```text
setlocal spelling=~/.vim/spell/en.utf-8.add
setlocal spelling=~/mySpell/myWord.utf-8.add
```

`1zg` 代表存在 en.utf-8.add  
`2zg` 代表存在 myWord.utf-8.add

`set spelllang`  
設定拼寫語言  
例如  
`set spelllang=en_us,nl`  
設定為美式英語、荷蘭語

## setlocal 跟 set

`setlocal`  
只會影響當前視窗或緩衝區

`set`  
全局影響

## 特殊用法

`set`  
顯示自己設定的環境設定

`set all`  
顯示所有的環境設定

有些設定在前面加 no 就會關閉此功能  
例如

```text
set spell
set nospell
```

`set spell!`  
加 ! 就會反轉該設定，開變關，關變開

`set spell?`  
加 ? 就可以獲得該設定的狀態

`set spell&`  
將該設定設定成預設值

