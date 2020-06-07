# 安裝 Nginx

## 說明

Nginx 為伺服器，一般安裝伺服器有 Apache 和 Nginx  
關於 Nginx 和 Apache 比較，這裡就不再多做說明  
主要以安裝 Nginx 為主

## 安裝

請先確保安裝之前，沒有其他程序佔用 80 port 或 443 port  
80 port 是 http  
443 port 是 https

### 使用套件管理器安裝

先更新套件管理器再安裝 Nginx  
安裝之前會告訴你將要安裝哪些套件，你需要先按 Y\(yes\) 確認

```text
$ sudo apt update
$ sudo apt install nginx
```

安裝完成後會自己啟動

### 檢查安裝是否成功

```text
$ sudo systemctl status nginx
```

你會看到一大堆訊息  
其中以下這條訊息 active \(running\)代表已經啟動了  
  
Active: **active \(running\)** since Fri 2020-06-05 14:27:00 UTC; 1 day 19h ago

如果你系統有設定防火牆，記得要打開 80 port 和 443 port

現在在瀏覽器輸入你的 Ubuntu IP 就會看到 Welcome to nginx  
http://你的IP

你的 IP 如果是雲端伺服器，應該會看到 IP 訊息  
如果是本機就看本機的網路 IP 即可

## 啟動關閉 Nginx

`$ sudo systemctl stop nginx`  
終止 Nginx

`$ sudo systemctl start nginx`  
啟動 Nginx

`$ sudo systemctl restart nginx`  
重新啟動 Nginx

`$ sudo systemctl reload nginx`  
重新載入 Nginx  
如果有修改配置，可以使用此指令

