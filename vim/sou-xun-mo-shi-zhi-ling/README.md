# 搜尋模式指令

`/<keyword>`  
正向搜尋

`?<keyword>`  
反向搜尋

## 轉義

加 \ 就是轉義  
正向查找時，/ 開頭的查找，要查找 / 時需要轉義變成 \/  
反向查找時，? 開頭的查找，要查找 ? 時需要轉義變成 \?  
要查找轉義 \ 也需要轉義，變成 \\

## 編輯

`<Ctrl-r><Ctrl-w>`  
搜尋到第一個匹配時，自動補全剩餘的單字  
但如果搜尋裡面有用[非常魔法](magic.md#fei-chang-mo-fa-very-magic)前綴，就會補全整個單字

## 搜尋偏移

在搜尋的結尾補上命令，例如 `/search/e`

匹配游標從結尾算起  
`[+num]` 結尾開始右移，`[-num]` 結尾開始左移  
`/e[+num]`  
`/e[-num]`

## 暫時關閉高亮

`:noh[lsearch]`  
如果打開 'hlsearch'，最後一次查找命令的所有匹配點都會被高亮。  
用 `:nohlsearch` 命令來暫停。

## 暫存器

`<Ctrl-r>{register}` 貼上暫存器的內容

## 替代

`:[range]s[ubstitute]/{pattern}/{string}/[flags]`  
搜尋一段文字，再用另一段文字將其替換

`:[range]&[&][flags] [count]`  
使用最後一次 `:substitute` 相同的模式和替代字串  
第二個 & 為使用最後一次的旗標

`{pattern}` 和 `{string}` 都適用正規表達式

執行 `{Vim Script}` 表達式，並將返回的結果作為替換 `{string}`  
`\={Vim Script}`

`~`  
使用上一個調用 `:substitute` 時的 `{string}`

### flags

`&`  
重用上一次 substitute 命令所用過的旗標

`I`  
區分大小寫

`c`  
確認或拒絕每一處的修改

| 提示 | 說明 |
| :--- | :--- |
| y | 替換此匹配 |
| n | 忽略此匹配 |
| q | 退出替換過程 |
| l | "last" - 替換此匹配後退出 |
| a | "all" - 替換此處與之後所有的匹配 |
| ^E &lt;Ctrl-e&gt; | 向上滾動視窗 |
| ^Y &lt;Ctrl-y&gt; | 向下滾動視窗 |

`e`  
屏蔽沒有匹配到該模式的錯誤提示訊息 "E486: 找不到模式"

`g`  
對行內所有的匹配進行替代

`i`  
忽略大小寫

`n`  
報告匹配的次數，並不實際進行替代

### 舉例

`:%s/jack/vick/g`  
將當前文件中所有的 jack 改成 vick

## vimgrep

vim 內部的 grep  
可以打開 [quickfix](../ex-ming-ling-mo-shi-zhi-ling/quickfix.md) 查看查詢結果

`:vimgrep /{pattern}/[g][j] {path/to/file}`  
把找到的匹配放到 quickfix 列表

`[g]`  
全域搜尋

`[j]`  
只更新 quickfix 列表

### 檔案路徑萬用字元

`**`  
對目錄遞迴搜尋

`*`  
通用檔名

#### 舉例

`**/*.txt`  
遞迴搜尋副檔名為 txt 的所有檔案

## grep

外部的 grep，就像系統的 grep 指令

`:gr[ep][!] [arguments]`  
搜尋結果會存放在 [quickfix](../ex-ming-ling-mo-shi-zhi-ling/quickfix.md) 列表

`:lgr[ep][!] [arguments]`  
搜尋結果會存放在當前視窗的位置列表

### 參數

-i 不區分大小寫

### 舉例

`:grep -r --include="*.txt" keyword path`  
遞迴搜尋 path 的所有 txt 檔，包含 keyword 的內容

## 尋找檔案

`:fin[d][!] [++opt] [+cmd] {file}`  
在 path 裡找到 `{file}` ，然後編輯 `:edit` 它  
  
`:set path+=path/**`  
增加 path

