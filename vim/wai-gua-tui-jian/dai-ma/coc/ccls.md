# ccls

## 介紹

ccls 是 language server

## 下載

{% embed url="https://github.com/MaskRay/ccls" %}

## 簡易說明

安裝過程有點複雜，作者使用 homebrew 安裝過程比較簡單一點

`$ brew install llvm`  
先安裝 llvm  
裡面有內建 clangd 也是一個 language server

`$ brew install ccls`  
再安裝 ccls

`$ xcode-select --install`   
mac os 如果找不到 stdio.h 標頭檔  
就安裝 command line tools

`:CocConfig` 設定 coc

{% code title="coc-settings.json" %}
```text
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
```
{% endcode %}

設定 ale

{% code title=".vimrc" %}
```text
let g:ale_cpp_ccls_init_options = {
\   'cache': {
\       'directory': '/tmp/ccls/cache'
\   }
\ }
```
{% endcode %}

