---
description: git 提交瀏覽器
---

# gv.vim

## 介紹

![git log &#x6A39;](../../../.gitbook/assets/image%20%288%29.png)

## 下載

{% embed url="https://github.com/junegunn/gv.vim" %}



## 安裝說明

須先安裝 [vim-fugitive](vim-fugitive.md)

使用插件管理器下載即可

{% code title=".vimrc" %}
```text
Plug 'tpope/vim-fugitive'
Plug 'junegunn/gv.vim'
```
{% endcode %}

## 常用指令

`:GV`  
打開 git 提交瀏覽器

`:GV!`  
打開 git 提交瀏覽器  
並只列出當前檔案有受影響的提交

### 在提交瀏覽器操作

`]]` 和 `[[`  
移動提交

`O`   
在新的標籤頁顯示提交內容

`o` 或 `<cr>`  
在分割視窗中顯示提交內容

`q` 或 `gq`  
離開



