# 操作終端機

## 說明

### tput

此指令可以用來控制終端機的行為，例如移動游標、清除畫面

## 指令參數

`cols`  
顯示視窗的寬度

`cup <row> <column>`  
移動游標到座標第 row 列，第 column 行

`el`  
清除到行尾

`rev`  
畫面反白

`rmul`  
結束底線模式

setaf {number}  
使用 ANSI escape code 設定前景\(字型\)顏色  
number 帶入數字  
0 紅色  
7 白色

`sgr0`  
選擇圖形渲染  
0 代表取消所有效果，重新設定

`smul`  
開始底線模式





