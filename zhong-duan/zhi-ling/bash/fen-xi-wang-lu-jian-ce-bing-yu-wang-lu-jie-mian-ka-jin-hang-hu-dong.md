# 分析網路，檢測並與網路介面卡進行互動

`$ arp -a`  
顯示位址解析表\(ARP table\)

`$ dig domainName mx`  
檢視 domain name server 資訊  
mx mail exchange server 郵件交換伺服器

`$ dig domainName ns`  
檢視 domain name server 資訊  
ns nameserver 伺服器名稱

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

## nc

nc 全名為 netcat 網路檢測工具

選項

-l 傾聽進入連線

-n 不要進行 DNS 搜尋

-v 顯示詳細模式

`nc -v www.oreilly.com 80`  
監聽 oreilly 80 port 網站是否能連線

### 兩台電腦連線傳送檔案

```text
# 接收檔案寫到 receiverData
nc -l 5000 > receiverData

# 傳送檔案到接收端
nc 網域或IP 5000 < senderData
```

