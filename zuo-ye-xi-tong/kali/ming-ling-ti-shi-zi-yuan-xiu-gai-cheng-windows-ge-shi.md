# 命令提示字元修改成 Windows 格式

Kali 命令提示字元是儲存在 PS1 環境變數

在 Kali 預設命令提示字元是  
使用者名稱@主機名稱:當前目錄  
userName@hostName:current\_directory

而目錄都是以 / 分割  
例如: /tmp/directory

假如要把命令提示字元偽裝成 windows，並以 \ 分割目錄  
例如：C:\tmp\directory

```text
$ PS1='C:${PWD/\//\\/g}>'
```

${...} 是正規表達式

${變數/尋找表達式/取代/旗標}

PWD 為顯示當前路徑  
尋找 / 因為 / 是特殊字元，所以前面加上 \  
取代 \ 因為 \ 是特殊字元，所以前面加上 \  
g 全域搜尋

