# Apache

## 說明

Apache 伺服器，mac os 原本就有安裝  
不過版本可能不是最新的

## 安裝

以下為安裝步驟

1. 停用 mac 原生的 Apache
2. 安裝 Apache

### 停用 mac 原生的 Apache

暫停原本 mac 的 apache  
`$ sudo apachectl stop`

關閉自動開啟  
`$ sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist 2>/dev/null`

### 安裝 Apache

使用 brew 安裝

更新 brew  
`$ brew update`

安裝 httpd  
`$ brew install httpd`

啟動 Apache 服務  
`$ sudo brew services start httpd`

重啟 apache  
`$ sudo apachectl -k restart`

## Apache 設定

編輯 `/usr/local/etc/httpd/httpd.conf` 檔案

將 `Listen 8080`   
改成 `Listen 80`

將 `DocumentRoot "/usr/local/var/www"`  
改成家目錄底下的 www 資料夾  
`DocumentRoot "/Users/yourName/www"`

將 `<Directory "/usr/local/var/www">`  
改成家目錄底下的 www 資料夾  
`<Directory "/Users/yourName/www">`

移除註解  
`LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so`

移除註解並改成  
`ServerName localhost`

移除註解  
`Include /usr/local/etc/httpd/extra/httpd-vhosts.conf`

重啟 apache  
`$ sudo apachectl -k restart`

## 設定 Virtual Host

原本應該有兩個範例，可以把它們註解，保留以下這個

{% code title="/usr/local/etc/httpd/extra/httpd-vhosts.conf" %}
```text
<VirtualHost *:80>
  ServerAdmin yourMail@mail.com
  DocumentRoot "/Users/yourName/www"

  <Directory "/Users/yourName/www">
      Options FollowSymLinks MultiViews
      AllowOverride All
      Order allow,deny
      Allow from all
  </Directory>
</VirtualHost>
```
{% endcode %}

## Apache 指令

`sudo apachectl start`  
開啟 apache

`sudo apachectl stop`  
關閉 apache

`sudo apachectl -k restart`  
重啟 apache

## 參考

{% embed url="https://www.ioa.tw/macOS/Apache.html" %}

裡面還有其他 apache 相關設定的教學  
作者這篇內容皆參考此篇文章而寫的

