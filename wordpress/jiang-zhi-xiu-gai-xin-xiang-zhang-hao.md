# 強制修改信箱帳號

## 說明

當你要修改管理員或使用者信箱帳號時，需要寄一封驗證信  
按確認之後才能改變，如果驗證信寄出不出又想要改變此欄位  
可以直接修改資料庫信箱的欄位，以下將告訴大家如何修改

## 修改步驟

因為登入 MySQL 的方式有很多種，作者在這就不再細說登入 MySQL 的問題  
一般都是使用 phpMyAdmin 登入，或者使用 MySQL Workbench  
亦或者是直接使用終端指令，登入的方式有很多種，只要連線的資料輸入正確即可

1. 登入要修改的 Wordpress 的 MySQL
2. 進入 Wordpress 資料庫的 wp\_options
3. 找到 option\_name 為 admin\_email 就是管理員信箱
4. 將此欄位的 option\_value 修改你要的信箱帳號

使用者的信箱在 wp\_users 資料表裡面的 user\_email 欄位  
找到 user\_login 為你要修改的帳號，並把 user\_email 改成你要的信箱即可

## 其他 - bitnami 登入 MySQL

作者是使用 bitnami wordpress，要登入 MySQL 可以參考以下連結

{% embed url="https://docs.bitnami.com/aws/faq/get-started/access-phpmyadmin/" %}



