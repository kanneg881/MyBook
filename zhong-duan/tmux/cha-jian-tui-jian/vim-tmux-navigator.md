# vim-tmux-navigator

## 說明

此插件為讓 vim 和 tmux 窗口移動保持一致的指令

## 官網

{% embed url="https://github.com/christoomey/vim-tmux-navigator" %}

## 安裝

使用插件管理器安裝

{% code title=".tmux.conf" %}
```text
set -g @plugin 'christoomey/vim-tmux-navigator'
```
{% endcode %}

輸入 `prefix` + I 安裝

## 指令

`<ctrl-h>`  
向左移動

`<ctrl-j>`  
向下移動

`<ctrl-k>`  
向上移動

`<ctrl-l>`  
向右移動

`<ctrl-\>`  
移動到上一個分割

