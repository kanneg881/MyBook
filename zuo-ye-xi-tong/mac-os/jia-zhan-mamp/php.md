# PHP

## 說明

PHP 是後端程式語言

## 安裝

使用 brew 安裝

先更新  
`brew update`

安裝  
`brew install php`

## 設定 Apache 可以執行 PHP

{% code title="/usr/local/etc/httpd/httpd.conf" %}
```text
# 載入 PHP 模組，請放到 LoadModule 最後面
# 請依照實際路徑設定，以下為作者開發時的路徑
LoadModule php_module /usr/local/opt/php/lib/httpd/modules/libphp.so

# 尋找此標籤，並修改成如下，預設讀取 index.php
<IfModule dir_module>
  DirectoryIndex index.php index.html
</IfModule>

# 新增此標籤，.php 檔都會被當作 PHP 執行
<FilesMatch \.php$>
  SetHandler application/x-httpd-php
</FilesMatch>
```
{% endcode %}

重啟 apache  
`$ sudo apachectl -k restart`

## 參考

{% embed url="https://www.ioa.tw/macOS/PHP.html" %}

裡面還有其他 PHP 相關設定的教學  
作者這篇內容皆參考此篇文章而寫的

