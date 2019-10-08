# ale

## 介紹

ALE \(異步 Lint 引擎\) 是一個提供 linting \(語法檢查和語義錯誤\) 插件  
並且還有許多功能，詳情到 Github 上看

## 下載

[https://github.com/dense-analysis/ale](https://github.com/dense-analysis/ale)

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

" 修正 PHP 檔使用 php-cs-fixer
" 修正 PHP 檔使用 phpcbf
let b:ale_fixers = {'php': ['php_cs_fixer', 'phpcbf']}
```

