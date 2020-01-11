# ftplugin

## 介紹

依檔案類型設定環境

## 說明

你會在 vim 資料夾裡找到 ftplugin 資料夾  
一般都是在家目錄底下  
~/.vim/ftplugin/

如果有設定[檔案類型 檢測 插件](../she-ding-huan-jing-zhi-ling.md#huan-jing-zhi-ling)  
你就可以在 ftplugin 依檔案類型個別[設定環境](../she-ding-huan-jing-zhi-ling.md)  
檔案命名方式為 filetype.vim

例如  
在 vimrc 已經設定縮排為 2  
只想在 c 語言檔時設定縮排為 4  
c 語言檔 filetype 是 c  
就在 ftplugin 資料夾底下建立 c.vim  
~/.vim/ftplugin/c.vim  
把要設定的環境寫在裡面

只要偵測到是 c 語言檔就會在 [vimrc](./) 執行完之後  
再執行 ~/.vim/ftplugin/c.vim

