# 原生插件管理\(

## 目錄

vim 會在 .vim/pack 目錄下搜尋插件目錄

首先在 .vim/pack 目錄下建立一個目錄  
.vim/pack/&lt;你的目錄&gt;

## opt

### 目錄位置

.vim/pack/&lt;你的目錄&gt;/opt/插件

### 說明

此目錄底下的插件，可用於手動載入

### 指令

`:packadd <目錄名稱>`  
手動載入插件

延遲載入方法

{% code title=".vimrc" %}
```text
" 當執行 :cmd 指令時才載入 <目錄名稱> 插件，並執行 :cmd
commannd ! -nargs=* cmd :packadd <目錄名稱> | cmd <f-args>

# 當文件類型為 type 時才載入 <目錄名稱> 插件，並執行插件指令
autocmd filetype type :packadd <目錄名稱> | {插件指令}
```
{% endcode %}

## start

### 目錄位置

.vim/pack/&lt;你的目錄&gt;/start/插件

### 說明

此目錄底下的插件，始終載入

## 設定

{% code title=".vimrc" %}
```text
" 載入 start 目錄中所有的插件
" 預設會在載入 .vimrc 之後自動執行
packloadall

" 載入所有插件的幫助文件
silent! helptags ALL
```
{% endcode %}

## 使用 git 管理插件

### 初始化 git 倉庫

```text
$ cd ~/.vim
$ git init
```

### 新增插件

```text
$ git submodule add https://github.com/{插件網址} pack/<你的目錄>/start/<目錄名稱>
$ git commit -am "add: <目錄名稱>"
```

### 更新插件

```text
$ git submodule update --recursive
$ git commit -am "mod: update plugins"
```

### 刪除插件

```text
$ git submodule deinit -f --pack/<目錄名稱>
$ rm -rf .git/modules/pack/<你的目錄>/start/<目錄名稱>
$ git rm -f pack/<你的目錄>/start/<目錄名稱>
```



