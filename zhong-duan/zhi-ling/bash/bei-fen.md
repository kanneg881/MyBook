# 備份

## dd

`$ dd if=inputFile of=outputFile`  
完整備份，一字不漏  
速度十分緩慢

{% tabs %}
{% tab title="舉例" %}
```text
$ dd if=/dev/sdb of=~/backup

備份隨身碟到家目錄，檔名為 backup
```
{% endtab %}
{% endtabs %}

### 選項

bs block size 區塊大小  
noerror 遇到錯誤時繼續進行

{% tabs %}
{% tab title="舉例" %}
```text
$ dd if=/dev/media of=~/backup bs=4096 conv:noerror

區塊大小為 4096 bytes，遇到錯誤時繼續進行
```
{% endtab %}
{% endtabs %}

