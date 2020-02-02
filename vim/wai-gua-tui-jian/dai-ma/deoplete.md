# deoplete

## 介紹

用於 Neovim / Vim8 的黑暗能量異步完成框架（從官網翻譯的...）  
這個框架需要另外下載自動完成的插件，才能算是有自動完成功能

當初在使用時有點一點卡頓的現象，目前作者改使用 [coc](coc/)

## 下載

{% embed url="https://github.com/Shougo/deoplete.nvim" %}

## 配置 .vimrc

```text
" 使用 deoplete
let g:deoplete#enable_at_startup = 1
" 設定每個檔案類型要用什麼提示，'_' 通用
call deoplete#custom#option('sources', {
    \ '_': ['buffer'],
    \ 'php': ['buffer', 'phpactor'],
    \})


```



