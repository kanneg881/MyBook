# alias

在終端如果指令太長的話就可以自己創別名，以縮短輸入指令數量  
以下說明如何永久生效別名

要使用別名可以直接在終端輸入指令

```text
$ alias ll='ls -l'

將 ls -l 縮寫成 ll
```

接著輸入 ll 就會有 ls -l 效果  
ls -l 說明在[這裡](./)

當你關閉終端機時就會發現，別名功能不見了  
所以要永久保留，以目前作者找到的方法為在 zsh 配置去做設定

首先編輯 .zshrc \(沒意外的話會在家目錄 ~/.zshrc \)

{% code title=".zshrc" %}
```text
# zsh 別名設定
source ~/.zsh/alias.zsh
```
{% endcode %}

意思為開啟終端時執行 ~/.zsh/alias.zsh 腳本  
而把別名都寫在 alias.zsh

{% code title="alias.zsh" %}
```text
# 打開 alias 檔案
alias aliasConfig='mvim ~/.zsh/alias.zsh'
```
{% endcode %}

這樣比較乾淨一點，如果求方便，也可以直接寫在 .zshrc  
寫好後要運行可以重啟終端機或者在終端輸入  
`$ source ~/.zshrc`

