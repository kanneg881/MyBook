---
description: 適用於 bash 指令
---

# bash

`$ command &`  
將 command 指令在背景執行

`$ compgen [-b][-c][-k]`  
顯示有哪些指令、內建功能、關鍵字  
-b 內建功能  
-c 指令  
-k 關鍵字

`$ dig domainName mx`  
檢視 domain name server 資訊  
mx mail exchange server 郵件交換伺服器

`$ dig domainName ns`  
檢視 domain name server 資訊  
ns nameserver 伺服器名稱

`$ fg PID`  
將在背景運行的程序叫回前端螢幕  
PID 為 process ID  
可以用 ps 查看 PID

`$ ls [-al] [path]`  
列出當前目錄中的檔案與子目錄  
-a 顯示隱藏檔案  
-l \(long listing\)詳細資料  
path 指定目錄

`$ lsmod`  
列出安裝在核心的模組

`$ modinfo moduleName`  
moduleName 模組名稱  
取得核心模組資訊

`$ ps [aux]`  
顯示所有系統上正在運行的程序  
a 顯示現有終端機下的所有程序，包括其他用戶的程序  
u 以用戶為主的格式來顯示程序狀況  
x 顯示所有程序，不以終端機來區分

`$ sysctl -a | less`  
列出顯示核心選項

`$ sysctl -p`  
修改完  /etc/sysctl.conf 核心選項  
執行此指令去執行修改

`$ type -t {word}`  
辨識 word 是關鍵字、內建功能、指令...  
例如 : $ type -t pwd 為內建功能

`$ uname -a`  
顯示版本資訊

`$ whoami`  
查看登入資訊

## 查看檔案

`$ head [-number] path/to/file`  
顯示檔案開頭 10 行  
-number 指定行數，例如 -20  
path/to/file 檔案位置

`$ less path/to/file`  
查看檔案內容  
按 `/` 可以搜尋關鍵字  
按 `n` 跳下一個  
英文有一句諺語 : less is more   
應對了  less 和 more 指令

`$ more path/to/file`  
查看檔案內容  
按 `<Enter>` 顯示下一行  
按 `q` 離開

`$ nl [option] path/to/file`  
顯示檔案內容，並顯示行號  
-ba 行數包含空白，預設不包含

`$ tail [-number] path/to/file`  
顯示檔案尾部 10 行  
-number 指定行數，例如 -20  
path/to/file 檔案位置

## 分析網路，檢測並與網路介面卡進行互動

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

service servicename start \| stop \| restart  
控制系統的背景服務  
servicename 服務名稱  
start \| stop \| restart 開啟 \| 終止 \| 重啟\(選一個\)

例如  
`$ service rsyslog stop`  
終止日誌服務



