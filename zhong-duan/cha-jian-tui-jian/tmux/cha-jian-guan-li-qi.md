# 插件管理器

方便安裝插件的管理器

## 安裝插件管理器

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

## 安裝插件

1. 新增插件到 `~/.tmux.conf` 如 `set -g @plugin '...'`
2. 輸入 `prefix` + I \(大寫 i，**I**nstall 的意思\) 獲取插件.

插件會克隆到 `~/.tmux/plugins/` 資料夾並執行

## 解除安裝插件

1. 到 `~/.tmux.conf` 移除插件，如 `set -g @plugin '...'`
2. 輸入 `prefix` + alt + u \(小寫 u，**u**ninstall 的意思\) 移除插件

所有插件都安裝到 `~/.tmux/plugins/`  
因此，您也可以在此處找到插件目錄並將其刪除。

