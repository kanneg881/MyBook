# 解決 git 衝突

當 git 發生衝突時  
使用 vimdiff 比較檔案的方式  
來修改檔案衝突

需先 [設定 git](jie-jue-git-chong-tu.md#she-ding-git) 才能使用 vimdiff

解決步驟如下

1. 打開 git 合併工具
2. 修改檔案
3. 提交

## 設定 git

```text
$ git config --global merge.tool vimdiff
使用 vimdiff 做為 git 的合併工具

$ git config --global merge.conflictstyle diff3
顯示兩個分支的共同祖先

$ git config --global merge.prompt false
禁止彈跳視窗提示
```

## 打開 git 合併工具

`$ git mergetool`

### 介面說明

上面三個由左至右為

* LOCAL：當前分支的檔案
* BASE：共同分支的檔案，在修之前的內容
* REMOTE：要合併分支的檔案

最下面為

* MERGED：最後要合併的檔案

## 修改檔案

在 MERGED 檔案進行操作

每一個差異都會有提示  
&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;  
差異內容  
&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;

只要移動到差異內容操作指令即可  
不需編輯內容

`[c` 和 `]c` 移動上/下一個差異

選擇要用哪個差異

`:diffg[et] BASE`  
選擇 BASE 檔案的差異

`:diffg[et] LOCAL`  
選擇 LOCAL 檔案的差異

`:diffg[et] REMOTE`  
選擇 REMOTE 檔案的差異

## 提交

修改完差異後可以將  
副檔名為 .orig 的檔案刪除後提交

刪除後執行提交

`$ git commit -m '解決衝突'`

