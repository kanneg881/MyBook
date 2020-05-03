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

## 選項類型

### 顯示選項

`$ tmux show -s`  
-s 顯示伺服器選項

`$ tmux show -g`  
-g 沒有其他的旗標為顯式全域會話選項

`$ tmux show -wg`  
-w 和 -g 一起為顯示全域窗口選項

`$ tmux show -g status`  
指定顯示 status 選項

### 改變選項

`set -g status off`  
設定狀態欄選項關閉

`set -s default-terminal 'tmux-256color'`  
設定預設終端選項

`set -gu status`  
-u 變成未設置選項，未設置選項會恢復成預設值

## 顏色和風格

`set -g status-style 'bg=blue'`  
設定狀態欄背景的顏色為藍色

剩下的風格項目寫在[手冊裡](https://man.openbsd.org/tmux#STYLES)

## 有用選項列表

除了樣式選項，這是最常用的 tmux 選項的簡短列表：

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x9078;&#x9805;</th>
      <th style="text-align:left">&#x985E;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">base-index</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x5982;&#x679C;&#x8A2D;&#x5B9A;&#xFF0C;&#x5247;&#x7A97;&#x53E3;&#x7D22;&#x5F15;&#x5F9E;
        base-index &#x958B;&#x59CB;&#x800C;&#x4E0D;&#x662F;&#x5F9E;0</td>
    </tr>
    <tr>
      <td style="text-align:left">buffer-limit</td>
      <td style="text-align:left">&#x4F3A;&#x670D;&#x5668;</td>
      <td style="text-align:left">&#x4FDD;&#x7559;&#x7684;&#x6700;&#x5927;&#x81EA;&#x52D5;&#x7DE9;&#x885D;&#x5340;&#x6578;&#xFF0C;&#x9810;&#x8A2D;&#x503C;&#x70BA;50</td>
    </tr>
    <tr>
      <td style="text-align:left">default-terminal</td>
      <td style="text-align:left">&#x4F3A;&#x670D;&#x5668;</td>
      <td style="text-align:left">tmux &#x4E2D; TERM &#x74B0;&#x5883;&#x8B8A;&#x6578;&#x7684;&#x9810;&#x8A2D;&#x503C;</td>
    </tr>
    <tr>
      <td style="text-align:left">display-panes-time</td>
      <td style="text-align:left">&#x7A97;&#x53E3;</td>
      <td style="text-align:left"><code>C-b q</code> &#x4EE5;&#x6BEB;&#x79D2;&#x70BA;&#x55AE;&#x4F4D;&#x7684;&#x6642;&#x9593;&#x986F;&#x793A;&#x7684;&#x7A97;&#x683C;&#x865F;</td>
    </tr>
    <tr>
      <td style="text-align:left">display-time</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x72C0;&#x614B;&#x6B04;&#x4E0A;&#x986F;&#x793A;&#x8A0A;&#x606F;&#x7684;&#x6642;&#x9593;&#xFF08;&#x4EE5;&#x6BEB;&#x79D2;&#x70BA;&#x55AE;&#x4F4D;&#xFF09;</td>
    </tr>
    <tr>
      <td style="text-align:left">escape-time</td>
      <td style="text-align:left">&#x4F3A;&#x670D;&#x5668;</td>
      <td style="text-align:left">tmux &#x6536;&#x5230; Escape &#x9375;&#x5F8C;&#x7B49;&#x5F85;&#x7684;&#x6642;&#x9593;
        <br
        />&#x4EE5;&#x67E5;&#x770B;&#x5B83;&#x662F;&#x5426;&#x662F;&#x8F03;&#x9577;&#x9375;&#x5E8F;&#x5217;&#x7684;&#x4E00;&#x90E8;&#x5206;</td>
    </tr>
    <tr>
      <td style="text-align:left">focus-events</td>
      <td style="text-align:left">&#x4F3A;&#x670D;&#x5668;</td>
      <td style="text-align:left">tmux &#x662F;&#x5426;&#x767C;&#x9001;&#x7126;&#x9EDE;&#x9375;&#x5E8F;&#x5217;&#xFF0C;&#x7576;&#x6D3B;&#x52D5;&#x7A97;&#x683C;&#x66F4;&#x6539;&#x6642;
        <br
        />&#x4EE5;&#x53CA;&#x662F;&#x5426;&#x5F9E;&#x5916;&#x90E8;&#x7D42;&#x7AEF;&#x63A5;&#x6536;&#xFF08;&#x5982;&#x679C;&#x652F;&#x6301;&#xFF09;</td>
    </tr>
    <tr>
      <td style="text-align:left">history-limit</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x6BCF;&#x500B;&#x7A97;&#x683C;&#x7684;&#x6B77;&#x53F2;&#x8A18;&#x9304;&#x4E2D;&#x4FDD;&#x7559;&#x7684;&#x6700;&#x5927;&#x884C;&#x6578;</td>
    </tr>
    <tr>
      <td style="text-align:left">mode-keys</td>
      <td style="text-align:left">&#x7A97;&#x53E3;</td>
      <td style="text-align:left">&#x5728;&#x5FA9;&#x5236;&#x6A21;&#x5F0F;&#x4E0B;&#x4F7F;&#x7528; emacs(1)&#x9084;&#x662F;
        vi(1) &#x9375;&#x7D81;&#x5B9A;</td>
    </tr>
    <tr>
      <td style="text-align:left">mouse</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x5982;&#x679C;&#x555F;&#x7528;&#x4E86;&#x6E38;&#x6A19;</td>
    </tr>
    <tr>
      <td style="text-align:left">pane-border-status</td>
      <td style="text-align:left">&#x7A97;&#x53E3;</td>
      <td style="text-align:left">&#x72C0;&#x614B;&#x6B04;&#x662F;&#x5426;&#x51FA;&#x73FE;&#x5728;&#x6BCF;&#x500B;&#x7A97;&#x683C;&#x908A;&#x6846;&#x4E2D;&#xFF1A;&#x9802;&#x90E8;&#x6216;&#x5E95;&#x90E8;</td>
    </tr>
    <tr>
      <td style="text-align:left">prefix</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x524D;&#x7DB4;&#x9375;&#xFF0C;&#x9810;&#x8A2D;&#x70BA; <code>C-b</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">remain-on-exit</td>
      <td style="text-align:left">&#x7A97;&#x53E3;</td>
      <td style="text-align:left">&#x7A0B;&#x5E8F;&#x5728;&#x904B;&#x884C;&#x96E2;&#x958B;&#x6642;&#x662F;&#x5426;&#x81EA;&#x52D5;&#x6BBA;&#x6B7B;&#x7A97;&#x683C;</td>
    </tr>
    <tr>
      <td style="text-align:left">renumber-windows</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x5982;&#x679C; on(&#x958B;)&#xFF0C;&#x5247;&#x7A97;&#x53E3;&#x5C07;&#x81EA;&#x52D5;&#x91CD;&#x65B0;&#x7DE8;&#x865F;
        <br
        />&#x4EE5;&#x586B;&#x88DC;&#x7A97;&#x53E3;&#x5217;&#x8868;&#x4E2D;&#x7684;&#x6240;&#x6709;&#x9593;&#x9699;</td>
    </tr>
    <tr>
      <td style="text-align:left">set-clipboard</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">
        <p>&#x7576;&#x8907;&#x88FD;&#x6587;&#x672C;&#x548C;&#x5916;&#x90E8;&#x7D42;&#x7AEF;&#x652F;&#x6301;&#x6642;</p>
        <p>tmux &#x662F;&#x5426;&#x61C9;&#x5617;&#x8A66;&#x8A2D;&#x5B9A;&#x5916;&#x90E8;
          X(7) &#x526A;&#x8CBC;&#x677F;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">set-titles</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x5982;&#x679C; on&#xFF0C;tmux &#x5C07;&#x8A2D;&#x5B9A;&#x5916;&#x90E8;&#x7D42;&#x7AEF;&#x7684;&#x6A19;&#x984C;</td>
    </tr>
    <tr>
      <td style="text-align:left">status</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x72C0;&#x614B;&#x884C;&#x662F;&#x5426;&#x53EF;&#x898B;</td>
    </tr>
    <tr>
      <td style="text-align:left">status-keys</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x5728;&#x547D;&#x4EE4;&#x63D0;&#x793A;&#x5B57;&#x5143;&#x4E0B;&#x662F;&#x5426;&#x4F7F;&#x7528;
        emacs(1) &#x6216; vi(1) &#x9375;&#x7D81;&#x5B9A;</td>
    </tr>
    <tr>
      <td style="text-align:left">status-interval</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x91CD;&#x756B;&#x72C0;&#x614B;&#x884C;&#x4E4B;&#x524D;&#x7684;&#x6700;&#x9577;&#x6642;&#x9593;&#xFF08;&#x4EE5;&#x79D2;&#x70BA;&#x55AE;&#x4F4D;&#xFF09;</td>
    </tr>
    <tr>
      <td style="text-align:left">status-position</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">&#x72C0;&#x614B;&#x884C;&#x7684;&#x4F4D;&#x7F6E;&#xFF1A;&#x9802;&#x90E8;&#x6216;&#x5E95;&#x90E8;</td>
    </tr>
    <tr>
      <td style="text-align:left">synchronize-panes</td>
      <td style="text-align:left">&#x7A97;&#x53E3;</td>
      <td style="text-align:left">&#x5982;&#x679C; on&#xFF0C;&#x5247;&#x5C07;&#x5728;&#x7A97;&#x53E3;&#x4E2D;&#x7684;&#x4EFB;&#x4F55;&#x7A97;&#x683C;&#x4E2D;&#x9375;&#x5165;&#x7684;&#x5167;&#x5BB9;
        <br
        />&#x767C;&#x9001;&#x5230;&#x7A97;&#x53E3;&#x4E2D;&#x7684;&#x6240;&#x6709;&#x7A97;&#x683C;
        - &#x8ACB;&#x8B39;&#x614E;&#x4F7F;&#x7528;&#x6B64;&#x9078;&#x9805;&#xFF01;</td>
    </tr>
    <tr>
      <td style="text-align:left">terminal-overrides</td>
      <td style="text-align:left">&#x6703;&#x8A71;</td>
      <td style="text-align:left">tmux &#x7684;&#x4EFB;&#x4F55;&#x529F;&#x80FD;&#x90FD;&#x61C9;&#x5F9E;&#x70BA;&#x5916;&#x90E8;&#x7D42;&#x7AEF;&#x6307;&#x5B9A;&#x7684;
        TERM &#x4E2D;&#x8986;&#x84CB;</td>
    </tr>
  </tbody>
</table>