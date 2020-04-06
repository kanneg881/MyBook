# tmux

## 介紹

tmux 為 Terminal Multiplexer 終端多工器簡稱，讓終端可以分割的插件，一般終端都是用標籤頁做切換，但沒辦法同時出現兩個終端在同一個標籤頁上，這個插件可以辦到。

![](../../../.gitbook/assets/tmux_with_panes.png)

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



