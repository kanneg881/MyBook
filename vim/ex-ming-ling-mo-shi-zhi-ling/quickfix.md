# Quickfix

`:cnext`  
跳轉到下一項

`:cprev`  
跳轉到上一項

`:cfirst`  
跳轉到第一項

`:clast`  
跳轉到最後一項

`:cnfile`  
跳轉到下一個文件中的第一項

`:cpfile`  
跳轉到上一個文件中的最後一項

`:cc N`  
跳轉到第 N 項

`:copen`  
打開 quickfix 視窗

`:cclose`  
關閉 quickfix 視窗

`:col[der] [count]`  
到前一個舊的錯誤列表。如果指定 `[count]`  
則執行 `[count]` 次。如果已經到達最舊的列表，則報錯。

`:cnew[er] [count]`  
到下一個新的錯誤列表。如果指定 `[count]`  
則執行 `[count]` 次。如果已經到達最新的列表，則報錯。

`:cdo {cmd}`  
在 quickfix 列表中的每一行執行 `{cmd}`

`:cfdo[!] {cmd}`  
在 quickfix 列表的每個文件上執行 `{cmd}`  
工作方式相當於：

```text
:cfirst
:{cmd}
:cnfile
:{cmd}
```

