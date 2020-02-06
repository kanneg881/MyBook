# E: unable to locate package

使用 apt-get 安裝套件時發生的錯誤

可能的原因是找不到倉庫

解決辦法如下

編輯 /etc/apt/sources.list  
使用 vim 或其他編輯器

加入以下內容

{% code title="sources.list" %}
```text
deb http://http.kali.org/kali kali-rolling main contrib non-free
```
{% endcode %}

更新 apt-get  
`$ apt-get update`

這時應該會跑一些東西  
接著再安裝一次套件  
`$ apt-get install 套件`

如果以上沒有解決問題，就只能再 google 看看是甚麼問題了

