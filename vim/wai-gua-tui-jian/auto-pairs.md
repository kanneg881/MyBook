# Auto Pairs

## 介紹

自動產生一對括號或成對的符號

## 下載

[https://github.com/jiangmiao/auto-pairs](https://github.com/jiangmiao/auto-pairs)

## 簡易說明

提供一些設定給您參考  
將程式寫到 .vimrc

```text
" 設定 php 檔標籤不要自動生成結束標籤 ?>
au FileType php let b:AutoPairs = AutoPairsDefine({}, ['<?', '<?php'])
" 關閉此功能，避免在 vim " 註解一直刪除空白行
let g:AutoPairsMultilineClose = 0
```

