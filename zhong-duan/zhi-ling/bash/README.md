---
description: 適用於 bash 指令
---

# bash

`$ !!`  
執行前一次執行的指令

`$ chsh -s /path/to/shell`  
切換終端預設的 shell  
例如：bash、fish、zsh

`$ compgen [-b][-c][-k]`  
顯示有哪些指令、內建功能、關鍵字  
-b 內建功能  
-c 指令  
-k 關鍵字

`$ curl [-A][-G][-I][-L][-d][-s][-o] outputFile URL`   
取得 URL 資料  
URL 網址  
-G 以 HTTP GET 傳送  
-I 取得協定\(HTTP、FTP\)標頭  
-L 網頁位置變更時，自行追蹤重導向  
-d 以 HTTP POST 傳送  
-o 把內容導向檔案  
-s 不顯示錯誤訊息或進度列  
outputFile -o 選項導向的檔案名稱

`$ date ['+format']`  
回傳時間戳記  
+ 格式化顯示時間  
例如：  
+%y%m%d %H%M%S  
%y 年，兩位數，例如：2019年 19  
%m 月，兩位數，例如：9月 09  
%d 日， 兩位數，例如：9日 09  
%H 24小時制，兩位數，例如：19點 19  
%M 分，兩位數，例如：9分 09  
%S 秒，兩位數，例如：9秒 09

`$ dig domainName mx`  
檢視 domain name server 資訊  
mx mail exchange server 郵件交換伺服器

`$ dig domainName ns`  
檢視 domain name server 資訊  
ns nameserver 伺服器名稱

`$ eval $command $argument`   
動態執行指令  
$command 指令變數  
$argument 參數  
例如：  
`$ eval ls -l`  
$command 為 ls  
$argument 為 -l

`$ ls [-a][-l][-s][-R] [path]`  
列出當前目錄中的檔案與子目錄  
a 顯示隱藏檔案  
l \(long listing\)詳細資料  
s 顯示檔案大小，單位為區塊  
R 找遍指定目錄的所有子目錄  
path 指定目錄

`$ lsmod`  
列出安裝在核心的模組

`$ man command`  
查看 command 指令的文件  
例如：`$ man ls`

`$ modinfo moduleName`  
moduleName 模組名稱  
取得核心模組資訊

`$ sudo command`  
使用超級使用者權限執行 command 指令  
例如：  
`$ sudo vim file`  
如果編輯檔案發現只能唯讀，代表權限不足  
就可以使用 sudo 獲得更高權限

`$ sysctl -a | less`  
列出顯示核心選項

`$ sysctl -p`  
修改完  /etc/sysctl.conf 核心選項  
執行此指令去執行修改

`$ type -t {word}`  
辨識 word 是關鍵字、內建功能、指令...  
例如 : $ type -t pwd 為內建功能

`$ uname [-a][-n]`  
顯示系統資訊  
-a 顯示版本資訊  
-n 顯示主機名稱

`$ whoami`  
查看登入資訊

## 分析網路，檢測並與網路介面卡進行互動

`$ arp -a`  
顯示位址解析表\(ARP table\)

`$ ifconfig`   
分析網路，檢測並與網路介面卡進行互動

`$ ifconfig eth0 xxx.xxx.xxx.xxx`  
更改 IP 位址，xxx 為數字

`$ ifconfig netmask xxx.xxx.xxx.xxx`  
更改網路遮罩，xxx 為數字

`$ ifconfig broadcast xxx.xxx.xxx.xxx`  
更改網路遮罩，xxx 為數字

`$ iwconfig`   
檢查無線網路裝置

`$ iwlist wlan0 scan`  
掃描可用 wifi  
wlan0 代表第0個  
用 iwconfig 先查看無線網路裝置

`$ netstat [-a][-n]`  
顯示網路連線  
-a 顯示所有連線以及接聽連接埠  
-n 以數字形式顯示位址與連接埠號

`$ ping ip`  
測試網路連線  
ip 網路位址  
例如：  
`$ ping 127.0.0.1`

### 竄改 MAC 位址

```text
$ ifconfig eth0 down
$ ifconfig eth0 hw ether 00:11:22:33:44:55
$ ifconfig eth0 up
```

## leafpad

leafpad 是文字編輯器

`$ leafpad fileName`  
打開 leafpad 文字編輯器並新增一個名為 fileName 的檔案

## 管理檔案系統與儲存裝置

`$ df [磁碟代號]`  
取得掛載中裝置的資訊  
\[磁碟代號\] sda sdb 等等

`$ fdisk -l`   
檢視磁碟分割

`$ fsck -p [/dev/sdb1]`  
檢查檔案系統錯誤，並修復  
-p 自動修復裝置上找到的問題  
\[/dev/sdb1\] 磁碟位置  
必須卸載才能檢查，見下面卸載指令

`$ lsblk`  
列出區塊裝置資訊

`$ mount`  
顯示檔案系統

`$ mount /name /mountPoint`   
手動掛載裝置  
/name 裝置名稱  
/mountPoint 掛載點  
例如  
mount /dev/sdb1 /mnt  
掛載 sdb1 硬碟於 /mnt

`$ umount /name`  
手動卸載裝置  
/name 裝置名稱

## 背景服務

控制系統的背景服務，指令如下

`$ service servicename start | stop | restart`  
控制系統的背景服務  
servicename 服務名稱  
start \| stop \| restart 開啟 \| 終止 \| 重啟\(選一個\)

例如  
`$ service rsyslog stop`  
終止日誌服務

## 遠端

`$ ssh userName@server`  
遠端連線  
userName 為使用者名稱  
server 為主機 IP

`$ ssh -l userName server`  
同上  
-l 後面為使用者名稱  
server 為主機 IP

`$ ssh server command > /path/to/file`  
遠端連線到 server 並執行 command  
把輸出重新導向到本地端的 /path/to/file

`$ ssh server command \> /path/to/file`  
同上，不過是把輸出重新導向到遠端的 /path/to/file

`$ ssh server bash < /path/to/file.sh`  
遠端執行本地端的 /path/to/file.sh  
輸出會重新導向到本地端

## 輸出

### echo

`$ echo "something"`  
輸出內容到螢幕上，會自動換行

### printf

`$ printf "something\n"`  
格式化輸出內容到螢幕上

`$ printf "%d" number`  
輸出變數 number  
%d 十進制

`$ printf "%x" number`  
輸出變數 number  
%x 十六進制

