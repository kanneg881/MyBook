# 解決 git 衝突

當 git 發生衝突時  
使用 vimdiff 比較檔案的方式  
來修改檔案衝突

## 設定 git

```text
$ git config --global merge.tool vimdiff
使用 vimdiff 做為 git 的合併工具

$ git config --global merge.conflictstyle diff3
顯示兩個分支的共同祖先

$ git config --global merge.prompt false
禁止彈跳視窗提示
```



