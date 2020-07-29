# 條件判斷

{% tabs %}
{% tab title="if else" %}
```text
if command
then
  do something
else
  do other thing
fi
```
{% endtab %}

{% tab title="case" %}
```
case "${var}" in
  a) $var 變數為 a
    do something
    ;;
  b) $var 變數為 b
    do something
    ;;
esac
```
{% endtab %}
{% endtabs %}

條件判斷中，0為真，非0為假

## if

`if (( $var > 0 ))`  
如果要比較數值則需用兩個括號表示  
否則比較的是詞語順序，也就是 2 &gt; 10 會是真值

`if [[ $var == '-i' ]]`  
如果要比較詞語順序則需用兩個中括號表示  
若想比較的是數值則使用兩個括號如上所述

