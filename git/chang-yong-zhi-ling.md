# 常用指令

`git add <檔案>`  
將檔案加入追蹤

`git commit [-a -m "訊息"]`  
提交追蹤的檔案  
-a add 追蹤  
-m 快速寫提交訊息  
沒有打 -m 會跳到編輯視窗用來輸入提交訊息

`git diff`  
顯示和前一個 commit 之間的差異，即修改哪些檔案

`git reset <參照> <檔案>`   
命令將檔案的狀態重設成未追蹤。

```text
$ git reset HEAD NewFile.txt
```

`git rm --cached fileName`  
將 fileName 檔案取消追蹤

`git status`  
顯示目前工作環境狀態



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

