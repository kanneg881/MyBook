# 重導向

將指令的輸入輸出導向到其它地方去，例如：檔案。

`command < inputData > outputData 2> error.log`  
將輸入導向到 inputData  
輸出導向到 outData  
錯誤導向到 error.log

輸出的1為一般輸出  
輸出的2為錯誤輸出

`command < inputData > outputData 2>&1`  
把錯誤訊息和正常輸出導向一起  
&1 的意思為，和1\(正常輸出\)一樣位置

`command < inputData &> outputData`  
同上，更為精簡的寫法



