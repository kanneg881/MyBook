# 輸出

## echo

`echo "$VAR"`  
輸出 VAR 變數到螢幕上  
輸出完內容後會換行  
如果只打 echo 等同於換行

`echo -e 'hello\nworld'`  
特殊字元將進行轉義  
例如 \n 將轉換成換行

## printf

`printf "%-10s %10d\n" "${text}" "${number}"`  
格式化輸出變數 ${text} 和 ${number} 的內容  
%-10s 為靠左對齊，固定10個字元  
%10d 為固定10個數字  
\n 為換行  
${text} 為第一個變數，對應 %-10s  
變數加雙引號是怕有空白，導致程式判斷錯誤  
${number} 為第二個變數，對應 %10d

`printf "%02x" $variable`  
輸出2位數16進制的數值，前面不足補0

`printf '%*s' $number $string`  
\* 代表字串長度為 $number  
s 代表字串為 $string

`printf -v VAR 'string'`  
將輸出的內容，儲存至 VAR 變數裡

### 格式化輸出時間

`printf '%()T'`  
輸出時間 時-分-秒  
例如：18時15分50秒

`printf '%()T' -1`  
輸出現在的時間  
-1 現在的時間  
例如：18時15分50秒

`printf '%(%F)T'`  
輸出時間 年-月-日  
例如：2020-09-06

其他格式化時間，可以參考  
strftime 系統程式庫

`man strftime`  
查看 strftime 文件

