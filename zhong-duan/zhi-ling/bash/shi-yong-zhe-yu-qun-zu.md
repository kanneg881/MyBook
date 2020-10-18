# 使用者與群組

## chmod

`$ chmod u={rwx},g={rwx},o={rwx} fileName`  
修改檔案的權限

u 使用者  
g 群組  
o 其他人  
r 讀取  
w 寫入  
x 執行

例如：  
`$ chmod u=rwx,g=rw,o=r fileNane`  
使用者有讀取、寫入、執行權限  
群組有讀取、寫入權限  
其他人有讀取權限

$ chmod {764} fileName  
修改檔案的權限

第1個數字代表使用者  
第2個數字代表群組  
第3個數字代表其他人

7 代表打開所有權限  
7 是由二進制 111 轉換

二進制的第1個數字代表為讀取  
二進制的第2個數字代表為寫入  
二進制的第3個數字代表為執行  
如果二進制是1代表開啟權限

111\(二進制\)  = 7\(十進制\)  
代表打開所有權限

110\(二進制\)  = 6\(十進制\)  
代表打開讀取、寫入

## chown

`$ chown {user} fileName`  
更改檔案持有的使用者

`$ chown :{group} fileNmae`   
更改檔案持有群組

## groups

`$ groups {user}`   
查看 user 隸屬哪些群組

## passwd

`$ passwd {user}`   
更改使用者密碼  
user 使用者名稱

