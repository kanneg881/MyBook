---
description: 可視化撤銷樹
---

# vim-mundo

## 介紹

顯示撤銷樹，選擇要撤銷到哪一步

![](../../../.gitbook/assets/image%20%287%29.png)

## 下載

{% embed url="https://github.com/simnalamburt/vim-mundo" %}

## 安裝說明

參考[下載](vim-mundo.md#xia-zai)頁面的 Installation  
使用插件管理器下載即可

## 常用指令

`:MundoToggle`  
打開撤銷樹

### 在撤銷樹中的操作

支援大部分[普通模式的移動](../../pu-tong-mo-shi-zhi-ling/yi-dong.md)方式

`<Enter>`  
選擇撤銷樹的節點

`?`  
幫助說明

`q`  
離開撤銷樹

## 配置 .vimrc

{% code title=".vimrc" %}
```text
" 儲存撤銷檔案在共用區
set undofile
" 撤銷檔案共用區路徑
set undodir=~/.vim/undo

```
{% endcode %}

