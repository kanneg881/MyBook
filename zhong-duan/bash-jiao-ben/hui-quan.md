# 迴圈

{% tabs %}
{% tab title="for" %}
```text
for VALUE in "${ARRAY[@]}"
do
  do something
done
```
{% endtab %}

{% tab title="while" %}
```
while command; do
  do something
done
```
{% endtab %}
{% endtabs %}

條件判斷中，0為真，非0為假

## for

for 會跑 $ARRAY 迴圈  
\[@\] 代表每一個元素都會取出  
之後取出的值會存在 VALUE 變數裡

## while

直到 command 為假為止

