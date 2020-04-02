# ctags

## 介紹

掃描程式碼庫，生成關鍵字索引  
可以快速跳到函數和類別定義之處  
一共有兩個版本  
Exuberant Ctags 不過好像很久沒更新了  
universal-ctags 上面的版本的衍生版，持續更新中  
作者是安裝 universal-ctags

## 下載

官網下載：  
[http://ctags.sourceforge.net](http://ctags.sourceforge.net)  
其他安裝方式（homebrew, yum...）：  
[https://packagecontrol.io/packages/CTags](https://packagecontrol.io/packages/CTags)  
universal-ctags github（裡面有 homebrew 指令安裝說明）：  
[https://github.com/universal-ctags/ctags](https://github.com/universal-ctags/ctags)

## 簡易說明

```text
$ ctags -R
```

從當前的工作目錄開始，遍歷所有的子目錄，並為其中的每一個文件建立索引。最終，再把這個標籤文件保存到當前工作目錄中。

