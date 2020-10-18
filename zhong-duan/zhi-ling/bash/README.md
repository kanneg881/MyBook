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

`$ eval $command $argument`   
動態執行指令  
$command 指令變數  
$argument 參數  
例如：  
`$ eval ls -l`  
$command 為 ls  
$argument 為 -l

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

