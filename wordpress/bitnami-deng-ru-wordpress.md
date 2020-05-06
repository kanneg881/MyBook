# bitnami 登入 Wordpress

## 登入

作者是使用 bitnami wordpress，要登入 MySQL 可以參考以下連結

{% embed url="https://docs.bitnami.com/aws/faq/get-started/access-phpmyadmin/" %}

## 修改 MySQL 密碼

因為嘗試了很多方式，都沒辦法使用 SQL 語法去修改，後來看到這篇才解決

{% embed url="https://docs.bitnami.com/installer/apps/espocrm/administration/change-reset-password/" %}

正常情況下，可以在資料庫下語法更改密碼  
讀者可以嘗試看看以下的做法

### 做法2

假設你已經登入 MySQL，在可以下語法的地方輸入資料庫指令

`show databases;`  
顯示資料庫，確認是否有找到 mysql 資料庫

`use mysql;`  
進到 mysql 資料庫

`show tables;`  
顯示資料表，確認是否有找到 user 資料表

`describe user;`  
顯示 user 資料表欄位，此時應該會看到 user 和 authentication\_string

`update user set authentication_string = PASSWORD("myPassword") where user = 'root';`  
修改 root 密碼為 myPassword  
這裡 root 為帳號，可以設定你要修改的帳號名稱  
myPassword 為密碼值，自行變更你想要的密碼

以上修改完成，如果找不到資料表或欄位名稱  
可能架構跟預設的不一樣，讀者需自行尋找  
基本上架構都差不多



