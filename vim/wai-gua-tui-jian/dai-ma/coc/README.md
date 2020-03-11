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

set hidden 等在[環境設定](../../../she-ding-huan-jing-zhi-ling/)有中文  
  
`:h coc-nvim.txt`  
詳情可以查看 coc 文件

{% code title=".vimrc" %}
```text
" 設定 node 路徑
let g:coc_node_path = "/usr/local/bin/node"

" if hidden is not set, TextEdit might fail.
set hidden

" Some servers have issues with backup files, see #649
set nobackup
set nowritebackup

" Better display for messages
set cmdheight=2

" You will have bad experience for diagnostic messages when it's default 4000.
set updatetime=300

" don't give |ins-completion-menu| messages.
set shortmess+=c

" always show signcolumns
set signcolumn=yes

" 使用 tab 觸發帶有幾個字元的補全並導覽
" 使用指令 ':verbose imap <tab>' 確定 tab 沒有被映射到其他插件
inoremap <silent><expr> <TAB>
      \ pumvisible() ? "\<C-n>" :
      \ <SID>check_back_space() ? "\<TAB>" :
      \ coc#refresh()
inoremap <expr><S-TAB> pumvisible() ? "\<C-p>" : "\<C-h>"

function! s:check_back_space() abort
  let col = col('.') - 1
  return !col || getline('.')[col - 1]  =~# '\s'
endfunction

" 使用 <c-space> 觸發補全
inoremap <silent><expr> <c-space> coc#refresh()

" 使用 <cr> 確認補全，`<C-g>u` 表示在當前位置斷開撤消鏈
" Coc 僅在確認時做片段和額外編輯
inoremap <expr> <cr> pumvisible() ? "\<C-y>" : "\<C-g>u\<CR>"

" 使用 `[g` 和 `]g` 瀏覽診斷
nmap <silent> [g <Plug>(coc-diagnostic-prev)
nmap <silent> ]g <Plug>(coc-diagnostic-next)

" 重新映射Gotos的鍵
nmap <silent> gd <Plug>(coc-definition)
nmap <silent> gy <Plug>(coc-type-definition)
nmap <silent> gi <Plug>(coc-implementation)
nmap <silent> gr <Plug>(coc-references)

" 使用 K 在預覽窗口中顯示文檔
nnoremap <silent> K :call <SID>show_documentation()<CR>

function! s:show_documentation()
  if (index(['vim','help'], &filetype) >= 0)
    execute 'h '.expand('<cword>')
  else
    call CocAction('doHover')
  endif
endfunction

" 高亮 symbol 在游標 CursorHold 時
autocmd CursorHold * silent call CocActionAsync('highlight')

" 重新映射以重命名當前單詞
nmap <leader>rn <Plug>(coc-rename)

" 重新映射格式化選定區域
xmap <leader>f  <Plug>(coc-format-selected)
nmap <leader>f  <Plug>(coc-format-selected)

augroup mygroup
  autocmd!
  " 設置 formatexpr 指定的 filetype(s).
  autocmd FileType typescript,json setl formatexpr=CocAction('formatSelected')
  " Update signature help on jump placeholder
  autocmd User CocJumpPlaceholder call CocActionAsync('showSignatureHelp')
augroup end

" 重新映射執行代碼選定區域的操作，例如：當前段落的<leader> aap
xmap <leader>a  <Plug>(coc-codeaction-selected)
nmap <leader>a  <Plug>(coc-codeaction-selected)

" 重新映射代碼執行當前行的操作
nmap <leader>ac  <Plug>(coc-codeaction)
" 修復當前可修復的第一個錯誤修復操作
nmap <leader>qf  <Plug>(coc-fix-current)

" 建立映射給函式文本物件，需要 languageserver 的 document symbols feature
xmap if <Plug>(coc-funcobj-i)
xmap af <Plug>(coc-funcobj-a)
omap if <Plug>(coc-funcobj-i)
omap af <Plug>(coc-funcobj-a)

" 使用 <TAB> 用於選擇範圍，必須 server 支援，像: coc-tsserver, coc-python
nmap <silent> <TAB> <Plug>(coc-range-select)
xmap <silent> <TAB> <Plug>(coc-range-select)

" 使用 `:Format` 格式化當前緩衝
command! -nargs=0 Format :call CocAction('format')

" 使用 `:Fold` 折疊當前緩衝
command! -nargs=? Fold :call     CocAction('fold', <f-args>)

" 使用 `:OR` 用於組織匯入當前緩衝區
command! -nargs=0 OR   :call     CocAction('runCommand', 'editor.action.organizeImport')

" 添加狀態行支持，以便與其他插件集成，查看 `:h coc-status`
set statusline^=%{coc#status()}%{get(b:,'coc_current_function','')}

" 使用 CocList
" 顯示所有診斷
nnoremap <silent> <space>a  :<C-u>CocList diagnostics<cr>
" 管理擴充
nnoremap <silent> <space>e  :<C-u>CocList extensions<cr>
" 顯示指令
nnoremap <silent> <space>c  :<C-u>CocList commands<cr>
" 尋找當前文件的 symbol
nnoremap <silent> <space>o  :<C-u>CocList outline<cr>
" 尋找 workspace symbols
nnoremap <silent> <space>s  :<C-u>CocList -I symbols<cr>
" 對下一項執行默認操作。
nnoremap <silent> <space>j  :<C-u>CocNext<CR>
" 對上一項執行默認操作。
nnoremap <silent> <space>k  :<C-u>CocPrev<CR>
" 恢復最新的 coc list
nnoremap <silent> <space>p  :<C-u>CocListResume<CR>
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

