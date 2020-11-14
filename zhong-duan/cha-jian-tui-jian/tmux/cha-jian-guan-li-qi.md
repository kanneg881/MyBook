# 插件管理器

方便安裝插件的管理器

## 安裝

要求: `tmux` 版本 1.9 \(或更高\), `git`, `bash`.

克隆 TPM:

```text
$ git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

## 配置

編輯 `~/.tmux.conf`

{% code title=".tmux.conf" %}
```text
# 插件清單
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'

# 其他範例:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'git@github.com:user/plugin'
# set -g @plugin 'git@bitbucket.com:user/plugin'

# 初始化TMUX插件管理器 (將此行保持在 tmux.conf 的最底部)
run '~/.tmux/plugins/tpm/tpm'
```
{% endcode %}

重新載入 TMUX 環境，以便獲得 TPM：

```text
# 如果 tmux 已經在運行，請在終端中輸入
$ tmux source ~/.tmux.conf
```

