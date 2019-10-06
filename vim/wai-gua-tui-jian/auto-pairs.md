# Auto Pairs

## 介紹

自動產生一對括號或成對的符號

## 下載

[https://github.com/jiangmiao/auto-pairs](https://github.com/jiangmiao/auto-pairs)

## 簡易說明

你可能在寫 PHP 檔時不想自動生成結束標籤  
將程式寫到 .vimrc

```text
" 設定 php 檔標籤不要自動生成結束標籤 ?>
au FileType php let b:AutoPairs = AutoPairsDefine({'<?' : '', '<?php' : ''})
```

