# 迴圈

{% tabs %}
{% tab title="for" %}
```text
# 第1種方法
for VALUE in "${ARRAY[@]}"
do
  do something
done

# 第2種方法
for (value in array) {
  do something
}

# 第3種方法
for (value=0;value<10;value++)
do
  do something
done

# 第4種方法
for (value=0; $#; value++)
do
  do something
  shift
done
```
{% endtab %}

{% tab title="while" %}
```
while command; do
  do something
done

# 將 while 裡面的輸出，都送至標準錯誤
while command
do
  do something
done >&2
```
{% endtab %}
{% endtabs %}

條件判斷中，0為真，非0為假

## for

for 會跑 $ARRAY 迴圈  
\[@\] 代表每一個元素都會取出  
之後取出的值會存在 VALUE 變數裡

第2種方法也會迭代迴圈  
取得 array 陣列的鍵值  
並存入到 value 變數裡  
寫法比較簡潔

第4種方法迭代參數的數量  
shift 會一直遞減參數，直到沒有參數為止

## while

直到 command 為假為止

