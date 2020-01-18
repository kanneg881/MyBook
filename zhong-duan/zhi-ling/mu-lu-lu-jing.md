# 目錄路徑

路徑有絕對路徑和相對路徑

絕對路徑：起始位置是根目錄的位置，根目錄前面沒有目錄了，  
一般都是 / 開頭

相對路徑：起始位置是相對於某個特定的位置

. 指的是當前目錄底下  
.. 指的是當前目錄的上一層目錄  
~ 指的是使用者目錄

假設使用者目錄在 /Users/Enjoy

```text
$ cd /Users
/Users

$ cd ./Enjoy
/Users/Enjoy

$ cd ..
/Users

$ cd /
/

$ cd ~
/Users/Enjoy
```

