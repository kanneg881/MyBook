# 快捷鍵

## 說明

介紹映射的使用方式，這些指令都可以寫在設定檔裡。

## 每個映射命令包含的模式

| 命令 | 一般 | 可視 | 選擇 | 插入 | 操作元等待 | 命令行 | Lang-Arg |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| map | ✓ | ✓ | ✓ |  | ✓ |  |  |
| nmap | ✓ |  |  |  |  |  |  |
| vmap |  | ✓ | ✓ |  |  |  |  |
| smap |  |  | ✓ |  |  |  |  |
| xmap |  | ✓ |  |  |  |  |  |
| omap |  |  |  |  | ✓ |  |  |
| map! |  |  |  | ✓ |  | ✓ |  |
| imap |  |  |  | ✓ |  |  |  |
| lmap |  |  |  | ✓ |  | ✓ | ✓ |
| cmap |  |  |  |  |  | ✓ |  |

後面每個映射指令都會使用前綴字加上映射指令  
例如  
刪除 map 指令為 unmap  
刪除 nmap 指令為 nunmap  
刪除 vmap 指令為 vunmap  
以此類推

## 映射指令說明

| 語法 | 說明 |
| :--- | :--- |
| {cmd} | 如上表中的 map, nmap, vmap 等 |
| {lhs} | 映射鍵 |
| {rhs} | 映射鍵執行的功能 |
| Leader | 此為設定鍵值的變數，預設為 \ |

## 設定 Leader

預設 leader 為 \

你可以更改 Leader 變數  
`:let mapleader = ","`

如上 Leader 變成 ,

使用 leader 範例  
`:map <Leader>a i`

輸入 \a 會變成 i   
假如 Leader 變數為 \  
i 為插入模式

## 設定遞迴映射語法

{cmd} {lhs} {rhs}

前面指定模式英文加上 map  
map, nmap, vmap...

舉例

`:imap a b`  
插入模式輸入 a 輸出 b

`:imap b a`  
插入模式輸入 b 輸出 a

因為遞迴的關係  
輸入 a 會輸出 b  
又因為輸入 b 會輸出 a  
造成無限循環，導致設定失敗  
這時就要用避免遞迴映射語法

## 設定避免遞迴映射語法

{cmd} {lhs} {rhs}

前面指定模式英文加上 noremap  
noremap, nnoremap, vnoremap...

舉例

`:inoremap a b`  
插入模式輸入 a 輸出 b

`:inoremap b a`  
插入模式輸入 b 輸出 a

因為避免遞迴的關係  
輸入 a 會輸出 b  
輸入 b 會輸出 a  
兩者不互相影響

## 刪除映射語法

{cmd} {lhs}

前面指定模式英文加上 unmap  
unmap, nunmap ,vunmap...

舉例

`:unnmap gq`  
刪除 gq 映射

## 常用指令

`:map`  
顯示映射指令表

`:h key-notation`  
查看按鍵英文名稱



