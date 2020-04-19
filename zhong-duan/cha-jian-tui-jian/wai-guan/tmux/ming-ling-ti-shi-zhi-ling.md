# 命令提示指令

## 說明

在 tmux 裡面的命令提示指令，但並不是在 tmux 裡的終端指令  
而是類似 Vim 的 [Ex命令模式指令](../../../../vim/ex-ming-ling-mo-shi-zhi-ling/)

此指令是會在狀態欄中出現 : 冒號提示輸入指令  
這時候輸入的指令才是  tmux 的命令提示指令

## 打開方式

`C-b :`  
切換命令提示，狀態欄會變成冒號 :

![](../../../../.gitbook/assets/tmux_command_prompt.png)

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

