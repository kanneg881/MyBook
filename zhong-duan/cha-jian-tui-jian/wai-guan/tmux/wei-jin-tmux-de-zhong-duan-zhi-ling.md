# 未進 tmux 的終端指令

## 建立會話

注意!不能在會話裡面建立會話

`$ tmux`  
一開始沒有會話時可以不帶參數

`$ tmux new-session`  
建立會話，名稱為按照數字順序  
new-session 縮寫為 new

`$ tmux new -smysession`  
建立會話，名稱為 mysession  
-s 指定會話名稱

`$ tmux new -d`  
建立會話  
-d 隱藏在背景

`$ tmux new -nmytopwindow top`  
建立會話，一開始的窗口名稱為 mytopwindow，運作 top 指令  
-n 指定一開始的窗口名稱

## 連接會話

`$ tmux attach`  
連接最近使用的會話，並且尚未連接的

`$ tmux attach -tmysession`  
連接指定會話名稱的會話  
-t 指定會話

`$ tmux attach -dtmysession`  
連接指定會話名稱的會話  
並且分離其他已經連接此會話的用戶  
注意這裡是 -dt\[會話名稱\]  
-d 分離其他已經連接此會話的用戶

`$ tmux new -Asmysession`  
建立會話，如果會話名稱存在就連接此會話  
注意這裡是 -As\[會話名稱\]  
-A 如果會話名稱存在就連接此會話  
-D 類似 attach -d ，分離其他已經連接此會話的用戶

## 列出會話

`$ tmux list-session`  
顯示可以連接的可用會話列表  
list-session 縮寫為 ls

