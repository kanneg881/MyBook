# 常用內建指令

`echo "$VAR"`  
輸出 VAR 變數到螢幕上

`getopts 'c:irR' opt;`  
不斷地取得選項  
例如上述會找到  
-c -i -r -R  
-c 冒號\(:\) 代表後面帶一個引數  
引數會被存在 OPTARG 變數  
找不到回傳 0  
可以搭配 while 迴圈一起使用

`read VAR`  
讀取使用者輸入的內容並存入 VAR 變數

