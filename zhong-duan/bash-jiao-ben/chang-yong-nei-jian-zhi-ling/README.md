# 常用內建指令

`getopts 'c:irR' opt;`  
不斷地取得選項  
例如上述會找到  
-c -i -r -R  
-c 冒號\(:\) 代表後面帶一個引數  
引數會被存在 `OPTARG` 變數  
變數 `OPTIND` 為正在處理的引數索引  
找不到則回傳非0值  
可以搭配 while 迴圈一起使用

`let a++`  
計算表達式，計算中的變數不需要加上 $  
如果有空格或特殊字元，則須加雙引號

`read VAR`  
讀取使用者輸入的內容並存入 VAR 變數

`read VAR VAR2`  
如果一行中超過一個字詞  
則第一個變數會寫入第一個字  
第二個變數會寫入第二個字  
剩下的會寫入最後一個變數  
如果字數不夠，則沒被寫入的變數會是 null 字串

`readarray -t ARRAY < "fileName"`  
讀取 fileName 的每一行資料，並將它存到 ARRAY 變數裡  
-t 為移除每一行的換行符號  
ARRAY 陣列變數  
"fileName" 檔案名稱

`unset $VAR`  
解除設置的變數
