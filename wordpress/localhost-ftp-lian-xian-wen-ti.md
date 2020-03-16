# localhost ftp 連線問題

當你在 localhost 更新 wordpress 時  
應該會發現需要輸入 ftp 帳號密碼  
因為在本機端，其實可以不需設定 ftp 連線  
但下一個問題是，檔案權限，和執行程式的權限不足

所以更新包含的問題有

1. 連線 ftp 需要帳號密碼
2. 檔案權限不足
3. 執行程式權限不足

## 連線 ftp 需要帳號密碼

在 config.php 檔新增以下設定

{% code title="wp-config.php" %}
```text
define('FS_METHOD','direct');
```
{% endcode %}

## 檔案權限不足

修改 wordpress 資料夾權限

`$ sudo chmod -R g+w wordpress`

## 執行程式權限不足

先查看執行 httpd 的擁有者是誰

`$ ps aux | grep httpd`

如果看到是 \__www  
則修改擁有者為 \__www

`$ sudo chown -R _www wordpress`



