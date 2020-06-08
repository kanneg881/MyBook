# 安裝 PHP

## 說明

說明如何在 Ubuntu 安裝 PHP，使用 Nginx 伺服器  
安裝完成後還需[配置 Nginx](an-zhuang-php.md#pei-zhi-nginx) 才能運行 PHP

## 安裝步驟

### 增加套件倉庫

最新版套件需要另外增加套件的倉庫

請先更新套件

`$ sudo apt update`

`$ sudo apt-get install python-software-properties  
$ sudo add-apt-repository ppa:ondrej/php`  
加入 ppa:ondrej/php 倉庫

安裝完再更新一次

`$ sudo apt update`

### 安裝 php-fpm

如果是使用 Nginx，請安裝 php-fpm

`$ sudo apt install php-fpm`

安裝過程裝，你會看到你安裝的 PHP 版本  
假設是 php7.4-fpm 就輸入以下指令檢查狀態

`$ systemctl status php7.4-fpm`

如果有看到以下內容代表正在運行中

```text
略
Active: active (running) 略
略
```

### 配置 Nginx

安裝完成後需要[配置](an-zhuang-nginx.md#pei-zhi-php) Nginx 才能運行 PHP 檔

