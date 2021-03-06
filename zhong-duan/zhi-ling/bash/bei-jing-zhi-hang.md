# 程序

`$ exec`  
Shell 內部命令，可以在運行中的 Shell 程序中執行的命令

`$ ps [aeux]`  
顯示所有系統上正在運行的程序  
a 顯示現有終端機下的所有程序，包括其他用戶的程序  
e 顯示執行中的背景  
u 以用戶為主的格式來顯示程序狀況  
x 顯示所有程序，不以終端機來區分

## 背景執行

`$ command &`  
將 command 指令在背景執行

`$ fg PID`  
將在背景運行的程序叫回前端螢幕  
PID 為 process ID  
可以用 ps 查看 PID

`$ kill PID`  
終止程序

`$ jobs`  
列出正在背景執行的工作

## 背景服務

控制系統的背景服務，指令如下

`$ service servicename start | stop | restart`  
控制系統的背景服務  
servicename 服務名稱  
start \| stop \| restart 開啟 \| 終止 \| 重啟\(選一個\)

例如  
`$ service rsyslog stop`  
終止日誌服務

## 排程

`$ crontab [-e][-l]`  
-e 編輯排程檔案  
-l 列出現有的 cron 排程檔案

### 編輯方式

在 cron 檔案內輸入如下指令

\* \* \* \* \* /path/to/script

\* \* \* \* \* 為時間設定  
例如：0 8 \* \* \* /path/to/script  
每天 8:00 執行腳本

script 要執行的腳本  
例如：scan.sh

### 時間設定

| 欄位 | 時間 | 設定值 |
| :--- | :--- | :--- |
| 1 | 分鐘 | 0 ~ 59 |
| 2 | 小時 | 0 ~ 23 |
| 3 | 日期 | 1 ~ 31 |
| 4 | 月份 | 1 ~ 12 |
| 5 | 禮拜幾 | 1 ~ 7 \(7 為星期日\) |

上面的欄位代表第幾個星號要取代的位置

## 連線

`exec FILE_DESCRIPTOR<>/dev/PROTOCOL/HOST/PORT`

FILE\_DESCRIPTOR 檔案描述符  
詳情可以參考[這裡](../../bash-jiao-ben/can-shu.md#dang-an-miao-shu-fu)

PROTOCOL 通訊協定，例如：TCP、UDP

HOST 主機 IP

PORT 通訊埠號

### 舉例

`exec 3<>/dev/tcp/192.168.10.1/25`  
內部指令連接 SMTP 伺服器，並存入在檔案描述符3

