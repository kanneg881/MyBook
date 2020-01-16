# coc

## 介紹

Coc 是 vim8 和 neovim 的智能感知引擎  
這是一個語法自動完成框架和語言服務器客戶端  
支持 VSCode 的擴展功能

## 下載

{% embed url="https://github.com/neoclide/coc.nvim" %}

## 簡易說明

### 安裝步驟

詳細安裝內容，請查看官方的安裝文件

1. 安裝 node
2. 安裝插件
3. 檢查服務狀態
4. 安裝擴充功能
5. 配置
6. 安裝 watchman \(可選\)

#### 安裝 node

安裝完 node 之後，要知道 node 位置，之後配置會用到

#### 檢查服務狀態

`g:coc_node_path`  
啟動服務狀態前，要先配置 node 執行位置  
配置到 .vimrc

`:checkhealth`  
在 neovim 可以輸入指令檢查

`:CocInfo`  
使用此指令查看服務資訊  
vim 可以用這個指令檢查服務狀態

#### 安裝擴充功能

`:CocInstall {name}`  
安裝擴充功能指令

`:CocInstall coc-json`  
首先安裝 coc-json，在設定 coc 時，是使用 json 格式

安裝其他擴充功能，可以到 npm 網站搜尋  
[https://www.npmjs.com/search?q=keywords%3Acoc.nvim](https://www.npmjs.com/search?q=keywords%3Acoc.nvim)

`:CocUninstall {name}`  
解除安裝擴充指令

`:CocUpdate`  
升級所有擴充，升級前請確保確保coc為最新版本  
例如如果是用 vim-plug 就用此插件的更新指令 `:PlugUpdate`

#### 配置

目前作者只有配置 node 路徑和快捷鍵到 .vimrc  
文件提到快捷鍵要自己綁定，讀者請自行定義即可  
詳情可以查看 coc 文件  
`:h coc-nvim.txt`

{% code title=".vimrc" %}
```text
" 設定 node 路徑
let g:coc_node_path = "/usr/local/bin/node"
" 快捷鍵 顯示當前位置下的錯誤信息，沒有截斷
map <leader>e <Plug>(coc-diagnostic-info)
" 快捷鍵 跳轉到下一個錯誤處
map <leader>en <Plug>(coc-diagnostic-next)
" 快捷鍵 跳轉到上一個錯誤處
map <leader>ep <Plug>(coc-diagnostic-prev)
" 快捷鍵 跳轉到定義位置
map <leader>def <Plug>(coc-definition)
" 快捷鍵 跳轉到宣告位置
map <leader>dec <Plug>(coc-declaration)
" 快捷鍵 跳轉到實現位置
map <leader>imp <Plug>(coc-implementation)
" 快捷鍵 跳轉到類型定義位置
map <leader>tdef <Plug>(coc-type-definition)
" 快捷鍵 跳轉到引用位置
map <leader>ref <Plug>(coc-references)
" 快捷鍵 跳轉到引用位置
map <leader>ref <Plug>(coc-references)
" 格式化選中區間
vmap <leader>f  <Plug>(coc-format-selected)
" 格式化 {motion}
nmap <leader>f  <Plug>(coc-format-selected)
" 格式化當前 buffer
map <leader>fb <Plug>(coc-format)
" 重新命名光標所在位置符號
map <leader>ren <Plug>(coc-rename)
" 獲取並執行 language server 給出的當前緩衝區的可用操作
map <leader>ca <Plug>(coc-codeaction)
" 獲取並執行 language server 給出的當前選擇區間內的可用操作
vmap <leader>cas  <Plug>(coc-codeaction-selected)
" 獲取並執行 language server 給出的當前 {motion} 的可用操作
nmap <leader>cas  <Plug>(coc-codeaction-selected)
" 打開游標位置下的鏈結
map <leader>ol <Plug>(coc-openlink)
" 修復當前可修復的第一個錯誤修復操作
map <leader>fix <Plug>(coc-fix-current)
" 打開重構窗口，用於重構當前函數或重命名
map <leader>rf <Plug>(coc-refactor)

```
{% endcode %}

`:CocConfig`  
開啟 coc 檔的指令  
預設檔案位置在 ~/.vim/coc-settings.json

diagnostic.displayByAle  
用 ale 顯示錯誤提示

{% code title="coc-settings.json" %}
```text
{
    "diagnostic.displayByAle": false,
    "explorer.icon.enableNerdfont": true,
    "languageserver": {
        "ccls": {
            "command": "ccls",
            "filetypes": ["c", "cpp", "objc", "objcpp"],
            "rootPatterns": [".ccls", "compile_commands.json", ".vim/", ".git/", ".hg/"],
            "initializationOptions": {
                "cache": {
                    "directory": "/tmp/ccls"
                }
            }
        }
    }
}
```
{% endcode %}

#### 安裝 watchman

watchman 是用來檢查擴充檔案變動，用來自動更新擴充

