# airline

## 介紹

美觀狀態欄和標籤欄  
還有一個叫 [powerline](../../../zhong-duan/cha-jian-tui-jian/wai-guan/powerline.md) 是給終端使用的，airline 是其衍生的產品

![demo](../../../.gitbook/assets/demo.gif)

![tab](../../../.gitbook/assets/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f3330363530322f313037323632332f34346332393261302d313439352d313165332d396365362d6463616461336631633533362e676966.gif)

## 下載

### airline

{% embed url="https://github.com/vim-airline/vim-airline" %}

### airline themes

{% embed url="https://github.com/vim-airline/vim-airline-themes" %}

## 簡易說明

建議一併下載 airline-themes

## 配置 .vimrc

此配置包含 airline themes 的配置，如果您沒下載 airline themes 配置只是浪費空間，不影響運作，我註解 airline theme 是因為我安裝其他的 theme。

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

