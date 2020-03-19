# ale

## 介紹

ALE \(異步 Lint 引擎\) 是一個提供 linting \(語法檢查和語義錯誤\) 插件  
並且還有許多功能，詳情到 Github 上看，有些語言需要額外配置，皆寫在此連結底下

## 下載

{% embed url="https://github.com/dense-analysis/ale" %}

## 簡易說明

| 指令 | 動作 |
| :--- | :--- |
| :ALEFix | 修正檔案問題 |
| :ALEFixSuggest | 建議修正問題 |

## 配置 .vimrc

```text
" remove_trailing_lines 刪除文件末尾的所有空白行
" trim_whitespace 刪除每行末尾的所有尾隨空格字元
let g:ale_fixers = {
\   '*': ['remove_trailing_lines', 'trim_whitespace'],
\}

" 修正 C 檔使用 clang-format
" 修正 HTML 檔使用 prettier
" 修正 JavaScript 檔使用 prettier_standard
" 修正 PHP 檔使用 php-cs-fixer
" 修正 PHP 檔使用 phpcbf
let g:ale_fixers = {
\   'c': ['clang-format'],
\   'html': ['prettier'],
\   'javascript': ['prettier_standard'],
\   'php': ['php_cs_fixer', 'phpcbf'],
\}

" 檢查 JavaScript 檔使用 standard
let g:ale_linters = {
\   'javascript': ['standard'],
\}

" 快速導覽錯誤
" ctrl + k 上一個錯誤
" ctrl + j 下一個錯誤
nmap <silent> <C-k> <Plug>(ale_previous_wrap)
nmap <silent> <C-j> <Plug>(ale_next_wrap)


```

