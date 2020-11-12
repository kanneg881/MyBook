---
description: 在 vim 操作 git
---

# vim-fugitive

## 介紹

在 vim 操作 git

## 下載

{% embed url="https://github.com/tpope/vim-fugitive" %}



## 安裝說明

使用插件管理器下載即可

{% code title=".vimrc" %}
```text
Plug 'tpope/vim-fugitive'
```
{% endcode %}

## 常用指令

`:Glog`  
同 git log  
會打開一個 [Quickfix](../../ex-ming-ling-mo-shi-zhi-ling/quickfix.md) 視窗  
可以此視窗指令操作 Quickfix 指令

`:Gstatus`  
同 git status

### 在 status 中的操作

支援大部分[普通模式的移動](../../pu-tong-mo-shi-zhi-ling/yi-dong.md)方式

`-`  
移入或移出 stage 區

`dd`  
在底下使用水平分割顯示檔案差異

`dv`  
在底下使用垂直分割顯示檔案差異

`g?`  
幫助說明

`gq`  
離開 status

## 配置 .vimrc

{% code title=".vimrc" %}
```text
" 儲存撤銷檔案在共用區
set undofile
" 撤銷檔案共用區路徑
set undodir=~/.vim/undo

```
{% endcode %}

