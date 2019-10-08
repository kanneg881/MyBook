# stratify

## 介紹

讓 vim 剛開始的畫面更漂亮，並且顯示一些常用的檔案  
方便快速開啟檔案，也可以自己定義自己常用的檔案

## 下載

[https://github.com/mhinz/vim-startify](https://github.com/mhinz/vim-startify)

## 簡易說明

`:Startify`  
打開 Startify 緩衝區

`q`  
關閉 Startify

可以把 .vimrc 加入到書籤  
把設定程式碼寫到 .vimrc

```text
" 加入書籤，格式：{'快捷鍵', '檔案'}
let g:startify_bookmarks = [
    \ {'c' : '~/.vimrc'},
    \ ]
```



