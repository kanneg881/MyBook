# 原生插件管理\(未完成\)

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
" 當執行 :cmd 指令時才載入並執行 <目錄名> 插件
commannd ! -nargs=* cmd :packadd <目錄名> | cmd <f-args>

# 當文件類型為 type 時才載入並執行 <目錄名> 插件
autocmd filetype type :packadd <目錄名> | {插件指令}
```
{% endcode %}

### start

#### 目錄位置

.vim/pack/&lt;你的目錄&gt;/start/插件

此目錄底下的插件，始終載入



