# 命令提示指令

## 說明

在 tmux 裡面的命令提示指令

## 打開方式

`C-b :`  
切換命令提示，狀態欄會變成冒號 :

![](../../../../.gitbook/assets/tmux_command_prompt.png)

多個指令，可以用分號 ; 區隔

## 指令

`:kill-server`  
殺死會話\(刪掉的意思\)

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

