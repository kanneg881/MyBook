# Javascript

## 介紹

standard 是語法檢查用  
prettier-standard 是格式化成 standard 用，有些需要手動修改

作者使用的是 JavaScript Standard Style，它是一種程式風格，規定程式碼要怎麼寫

{% embed url="https://standardjs.com/rules-zhtw.html" caption="standard 規則" %}

## 下載

{% embed url="https://github.com/standard/standard/blob/master/docs/README-zhtw.md" %}

{% embed url="https://github.com/sheerun/prettier-standard" %}

## 簡易說明

安裝步驟如下

1. 安裝 standard，[下載](javascript.md#xia-zai)的 standard 連結有詳細說明
2. 安裝 prettier-standard，[下載](javascript.md#xia-zai)的 prettier-standard 連結有詳細說明
3. 配置 .vimrc 已經寫在[ale 配置 .vimrc](./#pei-zhi-vimrc)

### 手動修改說明

a == b  
它會建議把 == 改成 ===  
這可能並不是你想要的，所以 prettier-standard 就不會自動修改

### 部分 standard 終端指令

`$ standard`   
在當前目錄下檢查所有 JavaScript 檔案的樣式

`$ standard "src/util//*.js" "test//*.js"`  
選擇性的檢查部分目錄們（請確保路徑前後有引號，避免出錯）

`$ standard --fix`  
自動化修正，如有輸入 `standard` 指令有提示輸入 standard --fix 修正時，它就會自動修正，有些問題需要手動修正，不過如果安裝完 prettier-standard 之後可以在 vim 輸入 `:ALEFix` 修正

prettier-standard 終端指令請自行參考官網說明

