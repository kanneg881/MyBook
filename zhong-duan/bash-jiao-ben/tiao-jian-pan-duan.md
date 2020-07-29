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

