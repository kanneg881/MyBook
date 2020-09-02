# 捕捉中斷

`trap command signal`  
用 trap 捕捉中斷，如果捕捉到則執行 command 指令  
 signal 中斷訊號  


例如：  
`trap date SIGINT`  
捕捉到後 SIGINT 訊號，就執行 date

## 訊號

SIGINT  
中斷正在執行的程序

SIGUSR1  
使用者可以自己呼叫的訊號

SIGUSR2  
使用者可以自己呼叫的訊號



