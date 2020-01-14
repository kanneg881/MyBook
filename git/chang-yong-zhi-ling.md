# 常用指令

## 配置

`git config <key>`  
檢視某個設定目前的值

```text
$ git config user.name
Enjoy
```



`git config [--level] --list`  
列出所有 Git 在目前位置能找到的設定值  
--level 有三個層級

1. --system  系統所有使用者和使用者倉儲的預設設定
2. --global 使用者帳號專用的設定
3. 未填寫 這個倉儲的專用設定

```text
$ git config --list
user.name=Relax
user.email=relax@example.com
...

$ git config --global --list
user.name=Enjoy
user.email=enjoy@example.com
...
```



`git config [--level] <key> <value>`  
設定 git 環境  
--level 層級  
&lt;key&gt; 環境參數  
&lt;value&gt; 設定值

層級優先權  
未填寫 &gt; global &gt; system  
層級優先權高的會覆蓋優先權低的設定  
global 會覆蓋 system

```text
$ git config user.name "Relax"
$ git config --global user.name "Enjoy"
```

