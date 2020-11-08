# 分析插件

## 說明

當插件太多時，可能會造成 vim 延遲的問題  
這邊教大家如何分析插件

## 分析啟動時間

剛開啟 vim 時，vim  會載入一些插件  
如果發現開啟 vim 要等一段時間時，就可以分析看看  
是什麼插件導致延遲的

`$ vim --startuptime path/to/file`  
將 vim 運行的日誌記錄到 path/to/file 裡

你會看到如下格式

281.222 000.605 000.605: sourcing ~/.vim/plugged/vim-surround/plugin/surround.vim

281.222  
第1段 vim 啟動經過的毫秒數

000.605  
第3段 載入插件佔用的毫秒數

~/.vim/plugged/vim-surround/plugin/surround.vim  
最後一段 插件位置

## 行為分析

針對特定的行為分析 vim 執行速度

開啟 vim 執行以下指令

```text
:profile start path/to/file
:profile func *
:profile file *
```

執行要檢測的行為

例如：  
`:CocCommand explorer`

`:q`  
接著退出 vim

打開 path/to/file 檔案

移動到檔案最下方

FUNCTIONS SORTED ON SELF TIME  
這段是函式列表

從列表中的 total 就可以看出哪個是最耗時間





