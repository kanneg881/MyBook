---
description: JSON 剖析器
---

# jq JSON 剖析器

## 介紹

jq 是輕量級且靈活的命令行 JSON 處理器。

## 下載

mac os 系統可以使用 brew 套件管理器安裝  
`brew install jq`

{% embed url="https://stedolan.github.io/jq/" %}

其他系統可以參考官網

## 簡易說明

`$ jq '.name' fileName.json`  
取得 fileName.json 裡的 name 鍵的值  
例如："name": "Andy"  
取得 "Andy"

`$ jq '.students[].name' fileName.json`  
取得 fileName.json 裡的  
students 陣列裡的 name 鍵的值

例如：

```text
"students": [
    {
      "name": "student1",
      "number": "1"
    },
    {
      "name": "student2",
      "number": "2"
    }
  ]
```

取得：  
"student1"  
"student2"

