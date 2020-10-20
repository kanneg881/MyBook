# 重導向

將指令的輸入輸出導向到其它地方去，例如：檔案。

`$ command < inputData > outputData 2> error.log`   
將輸入導向到 inputData  
輸出導向到 outputData  
錯誤導向到 error.log  
輸出會覆蓋檔案

輸出的1為一般輸出  
輸出的2為錯誤輸出

`$ command < inputData >> outputData`  
輸出覆加到 outputData，而不是覆蓋

`$ command < inputData > outputData 2>&1`  
把錯誤訊息和正常輸出導向一起  
&1 的意思為，和1\(正常輸出\)一樣位置

`$ command 2>&1 > outputData`  
把標準錯誤導向到標準輸出  
再把標準輸出導向到 outputData  
與上述順序不同，此標準輸出已變成錯誤訊息

`$ command < inputData &> outputData`  
同上，更為精簡的寫

`$ command < inputData > /dev/null`  
捨棄輸出

`$ command < inputData | tee [-a] outputData`  
將輸出導向到 outputData 並顯示在螢幕上  
-a 以覆加檔案的方式

## xargs

`$ command1 | xargs [-d] '\n' command2`  
xargs 為將 command1 的輸出導向給 xargs  
做為標準輸入，並分割後做為 command2 的參數  
-d 指定分割符號，預設為空白和換行，\n 為換行\(mac 沒有此指令\)

### 舉例

`$ ls . | xargs cat`  
將當前資料夾的所有檔名導向給 xargs 做為標準輸入  
並分割後做為 cat 的參數  
所以這裡會標準輸出此資料夾下的所有檔案  


