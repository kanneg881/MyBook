# 函式

```text
function functionName ()
{
  do something
}

functionName
```

將函式命名 functionName  
之後呼叫函式，則直接呼叫該名稱

`functionName "$VAR"`  
函式如同指令可以在後面放引數

## 區域變數

```text
function functionName ()
{
    local -i var var2
}
```

宣告區域變數 var var2  
-i 定義成整數

## 重導向

```text
function functionName ()
{
  echo 'error'
} >&2
```

函式可以把錯誤訊息導向到標準錯誤輸出

