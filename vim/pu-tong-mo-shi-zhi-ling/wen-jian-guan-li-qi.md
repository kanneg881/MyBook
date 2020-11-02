# 文件管理器

## 說明

類似在作業系統打開目錄一樣  
在 vim 底下打開文件管理器，編輯文件

打開文件管理器請參考 Ex 命令模式指令  
底下的[文件管理器](../ex-ming-ling-mo-shi-zhi-ling/wen-jian-guan-li-qi.md)

## 指令

以下指令為在文件管理器操作的功能鍵

`Enter`  
打開文件或目錄

`-`  
上一層目錄

`D`  
刪除一個文件或目錄

`R`  
重新命名一個文件或目錄

## wildmenu

此功能為產生自動補全的文件名菜單

### 環境設定

`set wildmenu`  
需要先在 .vimrc 做[環境設定](../she-ding-huan-jing-zhi-ling/#huan-jing-zhi-ling)

### 指令

`<Down>`  
方向鍵向下，進入游標中的目錄

`<Up>`  
方向鍵向上，回上一層目錄

