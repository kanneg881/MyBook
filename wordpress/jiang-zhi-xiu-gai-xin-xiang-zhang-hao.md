# 強制修改信箱帳號

## 說明

當你要修改管理員或使用者信箱帳號時，需要寄一封驗證信  
按確認之後才能改變，如果驗證信寄出不出又想要改變此欄位  
可以直接修改資料庫信箱的欄位，以下將告訴大家如何修改

## 修改步驟

1. 登入要修改的 Wordpress 的 MySQL
2. 進入 Wordpress 資料庫的 wp\_options 資料表
3. 找到 option\_name 欄位為 admin\_email 就是管理員信箱
4. 將此欄位的 option\_value 修改你要的信箱帳號

因為登入 MySQL 的方式有很多種，作者在這就不再細說登入 MySQL 的問題  
一般都是使用 phpMyAdmin 登入，或者使用 MySQL Workbench  
亦或者是直接使用終端指令，登入的方式有很多種，只要連線的資料輸入正確即可

使用者的信箱在 wp\_users 資料表裡面的 user\_email 欄位  
找到 user\_login 為你要修改的帳號，並把 user\_email 改成你要的信箱即可

## 其他說明

作者還有看到 wp\_options 資料表，有 mailserver\_ 開頭的欄位  
推測這可能是寄信相關的設定值，當你寄不出信時，有可能跟這些設定值有關

可能 Wordpress 有使用者介面可以設定 mailserver  
這方面作者尚未研究，只能大概說明一下  
因為不確定如何正確設定 mailserver  
所以直接修改資料庫  mailserver\_ 開頭的欄位  
不知道會不會產生漏洞，讀者再自行上網研究看看



