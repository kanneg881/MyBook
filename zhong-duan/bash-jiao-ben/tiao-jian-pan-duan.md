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
  a) # $var 變數為 a
    do something
    ;;
  b) # $var 變數為 b
    do something
    ;;
  [Cc]) # $var 變數為 C 或 c 都可
    do something
    ;;
esac
```
{% endtab %}

{% tab title="&&" %}
```
((1 > 0)) && do something
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

`if [[ !$boolean ]]`  
判斷式為否才成立

`if [[ $VAR ]]`  
如果變數不存在則為偽

`if [[ -e "$FILE" ]]`  
檢查檔案是否存在  
$FILE 檔案位置

`if [[ -r "$FILE" ]]`  
檢查檔案存取權限  
$FILE 檔案位置

`if [[ -s "$FILE" ]]`  
如果檔案大小大於0則為真，代表不是空檔案  
-s 測試檔案大小  
$FILE 檔案位置

## &&

左邊為 true 時，才會執行右邊的程式

例如：  
`((1 > 0)) && a=1`  
如果 1 &gt; 0 則 a = 1

`[[ "$1" =~ regular expression ]] && a=1`  
如果第一個參數匹配後面的正規表達式則 a=1

`[[ -n $var ]] && a=1`  
如果 $var 有值的話，則 a=1

