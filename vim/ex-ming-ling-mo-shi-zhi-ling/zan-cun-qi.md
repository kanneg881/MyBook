# 暫存器

`:reg`  
顯示暫存器清單

`:reg[isters] {arg}`  
顯示 {arg} 裡提到的編號和命名暫存器的內容  
例如:  
`:reg 1a`  
顯示暫存器 '1' 和 'a'  
{arg} 裡可以用空格  
  
`:[line]pu[t] [x]`  
放置文本 \[從寄存器 x\] 在行號 \[line\] \(缺省為當前行\) 之後

## 特殊符號

暫存器清單有些按鍵使用特殊符號表示

| 符號 | 按鍵 |
| :--- | :--- |
| ^\[ | Esc |
| ^M | Enter |

