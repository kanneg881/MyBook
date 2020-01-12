# C

## 介紹

C語言格式化文件，需先安裝 [ale](./)

## 下載

{% embed url="https://www.npmjs.com/package/clang-format" %}

## 簡易說明

到[下載](c.md#xia-zai)看安裝方式，然後配置 [.vimrc](./#pei-zhi-vimrc) 就能使用

## C 語言編譯指令

如果是 mac os 本身就有內建 clang，如果沒有請先自行安裝

| 指令 | 動作 |
| :--- | :--- |
| `$ clang --help` | 顯示可用的選項 |
| `$ clang --version` | 印出版本資訊 |
| `$ clang -o filename filename.c` | 指定將 filename.c 寫入 filename |

編譯 c 語言如下

```text
$ clang -o file file.c
$ ./file
輸出內容
```

`$ clang -o file file.c`  
生成一個 file 檔

`./file`  
意思為執行在此目錄生成的 file 檔

