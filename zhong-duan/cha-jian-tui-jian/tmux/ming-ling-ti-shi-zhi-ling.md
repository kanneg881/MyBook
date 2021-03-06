# 命令提示指令

## 說明

在 tmux 裡面的命令提示指令，但並不是在 tmux 裡的終端指令  
而是類似 Vim 的 [Ex命令模式指令](../../../vim/ex-ming-ling-mo-shi-zhi-ling/)

此指令是會在狀態欄中出現 : 冒號提示輸入指令  
這時候輸入的指令才是  tmux 的命令提示指令

## 打開方式

`C-b :`  
切換命令提示，狀態欄會變成冒號 :

![](../../../.gitbook/assets/tmux_command_prompt.png)

多個指令，可以用分號 ; 區隔

## 指令

`:kill-server`  
殺死會話\(刪掉的意思\)

`:kill-session`  
殺死連接的會話和它的所有窗口並且分離客戶端

`:neww command`  
新增一個視窗，並下 command 指令

`:neww -dnmynewwindow`  
新增一個視窗名為 mynewwindow，並且不進入此視窗  
不讓此視窗為當前視窗  
注意這裡為 -dn\[視窗名稱\]  
-d 不進入此視窗  
-n 命名視窗

`:neww -t999`  
新增一個視窗，索引值為 999  
-t 指定索引值

### 交換和移動

標記的方式，使用 tmux 的[快捷鍵](jin-ru-dao-tmux-de-kuai-jie-jian.md#jiao-huan-he-yi-dong)

`:swap-pane`  
跟標記的窗格交換

`:swap-window`  
跟標記的窗口交換

`:move-window -kt[number]`  
移動窗口  
-k 如果窗口存在會取代  
-t 指定窗口索引  
\[number\] 索引號碼

`:movew -r`  
重新整理窗口索引  
如果窗口索引為 1 20 30  
輸入完畢後會變成 1 2 3

### 複製和貼上

`:setb -bbuffer0 -nmybuffer`  
將貼上緩衝區 buffer0 更名成 mybuffer  
-b 存在的緩衝區名稱  
-n 更名的緩衝區名稱

`:setb -bfoo bar`  
建立緩衝區名為 foo，緩衝區的內容為 bar

`:loadb -bbuffername ~/a/file`  
建立緩衝區名為 buffername  
緩衝區的內容為 ~/a/file 檔案的內容

`set-buffer` 或 `load-buffer`  
縮寫為 `setb` `loadb`  
沒有用 -b 命名緩衝區名稱的話  
會自動建立緩衝區名稱

`:saveb -bbuffer0 ~/saved_buffer`  
保存緩衝區 buffer0 的內容到 ~/saved\_buffer 檔案裡  


