# coc-phpls

## 介紹

php 語法自動補全

## 下載

{% embed url="https://github.com/marlonfan/coc-phpls" %}

## 簡易說明

需要先安裝 [coc](./) 才能使用，安裝方式看下載連結就有  
安裝完就可以使用了

基本上不需要做什麼設定，如果要設定要在 Coc 設定檔做設定

`:CocConfig`  
打開 coc 設定檔

有兩個可以做設定  
intelephense.licenceKey 高級會員授權鑰匙  
phpls.enable 是否開啟，預設為 ture 開啟

{% code title="coc-setting.json" %}
```text
{
    "intelephense.licenceKey": "你的許可證密鑰",
    "phpls.enable": false
}
```
{% endcode %}

