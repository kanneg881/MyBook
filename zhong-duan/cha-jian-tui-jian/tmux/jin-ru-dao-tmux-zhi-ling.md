# 進入到 tmux 指令

`$ exit`  
離開 tmux

`$ tmux detach-client -a`  
分離連接此客戶端以外的所有客戶端

`$ tmux display-panes`  
顯示窗格號碼

`$ tmux kill-pane`  
殺死活動中的窗格

`$ tmux kill-window`  
殺死當前窗口，在此窗口中的所有窗格會一併刪除

`$ tmux rename-session sessionName`  
更改會話名稱為 sessionName

`$ tmux rename-window windowName`  
更改窗口名稱為 windowName

`$ tmux select-pane -t[number]`  
選擇活動窗格為 number  
number 為數字，用 `$ tmux display-panes`  查看

`$ tmux split-window -flag`  
分割窗口，可以搭配 flag  
-b 分割的窗口在左邊或上面  
-d 分割後不切換當前輸入指令的窗口  
-f 分割的窗口佔整個寬或高  
-h 水平分割，預設為右邊  
-v 垂直分割，預設為下面  
以上的參數同樣適用`new-session` 和 `new-window`

