# 配置 tmux

## 說明

當啟動 tmux 伺服器，tmux 在使用者的家目錄中運行一個名為   
.tmux.conf 的文件。 該文件包含按順序執行的 tmux 命令列表  
請務必注意 .tmux.conf 僅在啟動伺服器時運行  
而不在創建新會話時運行

可以使用 source-file 命令從 .tmux.conf 或正在運行的 tmux 伺服器  
運行不同的配置文件，例如使用命令提示符從正在運行的  
伺服器再次運行 .tmux.conf

```text
:source ~/.tmux.conf
```

配置文件中的命令每行顯示一個  
以＃開頭的任何行都是註釋，將被忽略

```text
# 這是一個註解 - 下面的命令為關閉狀態欄
set -g status off
```

## 使用滑鼠

`:set -g mouse on`  
打開滑鼠命令提示  
它可用於更改活動中窗格或窗口，調整窗格大小  
複製內容或從菜單中選擇項目

### 滑鼠操作說明

* 在窗格按左鍵切換活動中的窗格
* 在狀態欄的窗口名稱按左鍵切換窗口
* 按左鍵拖曳窗格邊距調整大小
* 在窗格內拖曳左鍵選取文字 放開滑鼠時複製選取的文字
* 在窗格按右鍵打開一個包含各種指令的選單 當釋放滑鼠後，選取的命令會在目標光格中運行 每一個選單項目也有一個快捷鍵顯示在括號中
* 在狀態欄的窗口或會話的名稱按右鍵打開一個 類似的選單給窗口或會話使用

## 快捷鍵綁定

使用 `bind-key` 和 `unbind-key` 命令可以更改 tmux 快捷鍵綁定  
tmux 中的每個快捷鍵綁定都屬於一個命名的快捷鍵表  
有四個預設的快捷表：

* root\(根\) 表包含不帶前綴鍵的快捷鍵綁定
* prefix\(前綴\) 表包含在前綴鍵按下之後的快捷鍵綁定 就像[進入到 tmux 的快捷鍵](jin-ru-dao-tmux-de-kuai-jie-jian.md)提到的那樣
* copy-mode\(複製模式\) 表包含使用 emacs\(1\)-style 的按鍵 在復制模式下使用快捷鍵綁定。
* copy-mode-vi 表包含使用 vi\(1\)-style 的按鍵 在復制模式下使用快捷鍵綁定。

可以使用 `list-keys` 命令列出所有的快捷鍵綁定或  
單個表的快捷鍵綁定。預設情況下，這會將按快捷鍵顯示為  
一系列的 bind-key 命令。  
-T 標誌 要顯示的快捷鍵表  
-N 標誌 顯示快捷鍵幫助，像是 `C-b？` 快捷鍵綁定

**作者在輸入 -N 時，已經變成非法的選項了**

例如，僅列出 prefix 表中的快捷鍵

```text
$ tmux lsk -Tprefix
bind-key    -T prefix C-b     send-prefix
bind-key    -T prefix C-o     rotate-window
...
```

或者

```text
$ tmux lsk -Tprefix -N
C-b     Send the prefix key
C-o     Rotate through the panes
...
```

綁定 `C-b M-0` 快捷鍵為選擇窗口 10

```text
bind M-0 selectw -t:=10
```

取消綁定快捷鍵 `C-b M-0`

```text
unbind M-0
```

更進一步綁定的部分在[手冊頁的命令部分](https://man.openbsd.org/tmux#COMMANDS)

### 複製模式快捷鍵

複製模式快捷鍵綁定在 copy-mode 和 copy-mode-vi 按鍵表中設定  
複製模式具有一組單獨的命令，這些命令使用 -X 標誌  
傳遞給 send-keys 命令，例如，複製模式 start-of-line 命令  
將游標移動到行的開頭，並綁定 C-a 到 copy-mode 按鍵表：

```text
$ tmux lsk -Tcopy-mode C-a
bind-key -T copy-mode C-a send-keys -X start-of-line
```

[手冊頁](https://man.openbsd.org/tmux#WINDOWS_AND_PANES)中提供了複製模式命令的完整列表，這裡是選取：

| 命令 | _emacs\(1\)_ | _vi\(1\)_ | 描述 |
| :--- | :--- | :--- | :--- |
| begin-selection | C-Space | Space | 開始選取 |
| cancel | q | q | 離開複製模式 |
| clear-selection | C-g | Escape | 清除選取 |
| copy-pipe |  |  | 複製並管道到第一個參數中的命令 |
| copy-selection-and-cancel | M-w | Enter | 複製選取並離開複製模式 |
| cursor-down | Down | j | 向下移動游標 |
| cursor-left | Left | h | 向左移動游標 |
| cursor-right | Right | l | 向右移動游標 |
| cursor-up | Up | k | 向上移動游標 |
| end-of-line | C-e | $ | 移動游標到行尾 |
| history-bottom | M-&gt; | G | 移至歷史底部 |
| history-top | M-&lt; | g | 移至歷史頂部 |
| middle-line | M-r | M | 移至中間行 |
| next-word-end | M-f | e | 移至下一個單字的節尾 |
| page-down | PageDown | C-f | 向下翻頁 |
| page-up | PageUp | C-b | 向上翻頁 |
| previous-word | M-b | b | 移至上一個單字 |
| rectangle-toggle | R | v | 切換矩形選取 |
| search-again | n | n | 重複上一次搜尋 |
| search-backward |  | ? | 向後搜尋，第一個參數是搜尋項目 |
| search-backward-incremental | C-r |  | 向後漸進搜尋，通常與 -i 標誌一起使用命令提示 |
| search-forward |  | / | 向前搜尋，第一個參數是搜尋項目 |
| search-forward-incremental | C-s |  | 向前漸進搜尋 |
| search-reverse | N | N | 重複上一次搜尋，但方向相反 |
| start-of-line | C-a | 0 | 移至行首 |

