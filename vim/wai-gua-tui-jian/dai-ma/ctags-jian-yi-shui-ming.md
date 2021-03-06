# ctags

## 介紹

掃描程式碼庫，生成關鍵字索引  
可以快速跳到函數和類別定義之處  
一共有兩個版本  
Exuberant Ctags 不過好像很久沒更新了  
universal-ctags 上面的版本的衍生版，持續更新中  
作者是安裝 universal-ctags

## 下載

{% embed url="http://ctags.sourceforge.net" caption="官網下載" %}

{% embed url="https://packagecontrol.io/packages/CTags" caption="其他安裝方式（homebrew, yum...）" %}

{% embed url="https://github.com/universal-ctags/ctags" caption="universal-ctags 官網（裡面有 mac os 安裝說明文件）" %}

{% embed url="https://github.com/universal-ctags/homebrew-universal-ctags" caption="universal-ctags（裡面有 homebrew 指令安裝）" %}



## 簡易說明

如果是 mac 建議安裝使用 homebrew  
只要下指令玩大致上就安裝好了

如果安裝的是 universal-ctags 可以檢查安裝版本，看是否安裝成功

### 檢查安裝版本

```text
$ ctags --version
```

### 使用說明

```text
$ ctags -R .
```

從當前的工作目錄開始，遍歷所有的子目錄，並為其中的每一個文件建立索引。最終，再把這個標籤文件保存到當前工作目錄中。

### 配置 .vimrc

{% code title=".vimrc" %}
```text
" 保存 python 檔案時，自動更新標籤
autocmd BufWritePost *.py silent! !ctags -R &
```
{% endcode %}

