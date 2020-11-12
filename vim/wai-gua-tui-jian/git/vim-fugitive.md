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

`:Gblame`  
同 git blame

`:Glog`  
同 git log

`:Gstatus`  
同 git status

### 在 :Gblame 中的操作

`<Enter>`  
打開檔案差異

`A`  
調整 blame 視窗大小，可看見提交、作者

`C`  
調整 blame 視窗大小，可看見提交

`D`  
調整 blame 視窗大小，可看見提交、作者、日期

`g?`  
幫助說明

`o`  
在分割視窗中打開選擇的檔案差異

### 在 :Glog 中的操作

會打開一個 [Quickfix](../../ex-ming-ling-mo-shi-zhi-ling/quickfix.md) 視窗  
可以此視窗指令操作 Quickfix 指令

### 在 :Gstatus 中的操作

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

