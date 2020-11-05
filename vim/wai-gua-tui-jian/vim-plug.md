# vim-plug

## 介紹

插件管理器，用起來比 Vundle 還方便  
在 .vimrc 裡面要打的內容較短，速度較快  
使用上跟 Vundle 差不多

## 下載

[https://github.com/junegunn/vim-plug](https://github.com/junegunn/vim-plug)

## 簡易說明

### 安裝

安裝有兩種方式，詳細做法請到官網查看

1. 下載 plug.vim並將其放在 .vim/autoload 資料夾中
2. 使用 curl 方式下載，這個指令可以放在 .vimrc 自動安裝

### 使用方式

到官網 Usage 的 Example 查看完整說明

以下簡單說明使用方式  
編輯 .vimrc 文件

{% code title=".vimrc" %}
```text
" 使用前先執行此程式
call plug#begin('~/.vim/plugged')

" 確定你使用單引號

" 所有有效的 git 網址
Plug 'https://github.com/junegunn/vim-github-dashboard.git'

" 簡寫; 取得 https://github.com/junegunn/vim-easy-align
Plug 'junegunn/vim-easy-align'

" 當有執行 :NERDTreeToggle 指令時再載入
Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }
" 只對特定文件類型載入
" 例如以下只對文件類型為 clojure 才載入
Plug 'tpope/vim-fireplace', { 'for': 'clojure' }

" 結束安裝插件呼叫此程式
call plug#end()
```
{% endcode %}

### 指令

| 指令 | 描述 |
| :--- | :--- |
| `PlugInstall [name ...] [#threads]` | 安裝插件 |
| `PlugUpdate [name ...] [#threads]` | 安裝或更新插件 |
| `PlugClean[!]` | 刪除未列出的插件（爆版清除沒有提示） |
| `PlugUpgrade` | 升級 vim-plug 自己 |
| `PlugStatus` | 檢查插件狀態 |
| `PlugDiff` | 檢查之前更新的更改和等待的更改 |
| `PlugSnapshot[!] [output path]` | 生成腳本以還原目前插件的快照 |

