# tmux

## 介紹

tmux 為 Terminal Multiplexer 終端多工器簡稱，讓終端可以分割的插件，一般終端都是用標籤頁做切換，但沒辦法同時出現兩個終端在同一個標籤頁上，這個插件可以辦到。

![](../../.gitbook/assets/tmux_with_panes.png)

## 下載

{% embed url="https://github.com/tmux/tmux" %}

## 安裝

安裝前先確定目前的系統是可以運作這個插件的  
OpenBSD, FreeBSD, NetBSD, Linux, OS X 和 Solaris

一般照上面官網的安裝方式有點複雜，作者在 Mac OS 沒有安裝成功，它依賴的套件有點不太清楚如何安裝，大家再自行研究。

Mac OS 上可以使用 brew 安裝，比較簡單，如下所示

```text
$ brew search tmux 
$ brew install tmux
```

安裝完，測試看看有沒有安裝成功

`$ tmux -V`  
查看 tmux 版本

## 說明

這邊簡要說明，詳細說明可以到[下載](./#xia-zai)頁面查看

以下用中文代稱  
pane 窗格  
window 窗口  
sessison 會話

下圖有三個窗格，其中一個窗格 active pane 為運作中的窗格，可以下指令的窗格，每個窗格用線區隔，運作中的窗格線為綠色，這三個窗格在一個窗口中，下圖顯示的窗口稱為當前的窗口，所以可能會有其它的窗口，一個會話存在多個窗口，會話可以有多個，所以下圖為目前會話中當前窗口的三個窗格，最下面綠色的是狀態欄

![](../../.gitbook/assets/tmux_pane_diagram.png)

* 程序在終端的窗格中運行，每個窗格都對應一個窗口
* 每個窗口都有一個名稱和一個運作的窗格
* 窗口連接到一個或多個會話
* 每個會話都有一個窗口列表，每個窗口都有一個索引。
* 顯示在會話中的窗口，為當前窗口
* 會話連接零到多個客戶端
* 每個客戶端連接到一個會話

### 狀態欄

![](../../.gitbook/assets/tmux_status_line_diagram.png)

\[0\] 會話名稱

0:man ~ 3:bash 窗口索引:窗口名稱  
太多窗口會以 &lt; 和 &gt; 代表箭頭後面還有的意思  
- 符號為上一個窗口  
\* 符號為當前窗口

"MacBook-Pro" 窗格名稱

10:33 22-Feb-20 時間

