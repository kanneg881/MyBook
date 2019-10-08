# airline

## 介紹

美觀狀態欄和標籤欄

![demo](../../../../.gitbook/assets/demo.gif)

![tab](../../../../.gitbook/assets/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f3330363530322f313037323632332f34.gif)

## 下載

[https://github.com/vim-airline/vim-airline](https://github.com/vim-airline/vim-airline)

## 簡易說明

建議一併下載 [airline-themes](airline-themes.md)

還有一個叫 powerline 是給終端使用的，airline 是其衍生的產品

## 配置 .vimrc

此配置包含 airline themes 的配置，如果您沒下載 airline themes 配置只是浪費空間，不影響運作。

```text
" 設定主題
" let g:airline_theme = 'violet'
" 當緩衝區修改時高亮
let g:airline_minimalist_showmod = 1
" 使用 powerline 外觀
let g:airline_powerline_fonts = 1
" 美觀標籤頁
let g:airline#extensions#tabline#enabled = 1
```
