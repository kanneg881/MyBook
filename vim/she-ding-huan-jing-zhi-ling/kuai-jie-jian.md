# 快捷鍵

## 說明

介紹映射的使用方式，這些指令都可以寫在設定檔裡。

## 每個映射命令包含的模式

| 命令 | 一般 | 可視 | 選擇 | 插入 | 操作元等待 | 命令行 | Lang-Arg |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| map | ✓ | ✓ | ✓ |  | ✓ |  |  |
| nmap | ✓ |  |  |  |  |  |  |
| vmap |  | ✓ | ✓ |  |  |  |  |
| smap |  |  | ✓ |  |  |  |  |
| xmap |  | ✓ |  |  |  |  |  |
| omap |  |  |  |  | ✓ |  |  |
| map! |  |  |  | ✓ |  | ✓ |  |
| imap |  |  |  | ✓ |  |  |  |
| lmap |  |  |  | ✓ |  | ✓ | ✓ |
| cmap |  |  |  |  |  | ✓ |  |

後面每個映射指令都會使用前綴字加上映射指令  
例如  
刪除 map 指令為 unmap  
刪除 nmap 指令為 nunmap  
刪除 vmap 指令為 vunmap  
以此類推

## 映射指令說明

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x8A9E;&#x6CD5;</th>
      <th style="text-align:left">&#x8AAA;&#x660E;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">{cmd}</td>
      <td style="text-align:left">&#x5982;&#x4E0A;&#x8868;&#x4E2D;&#x7684; map, nmap, vmap &#x7B49;</td>
    </tr>
    <tr>
      <td style="text-align:left">{lhs}</td>
      <td style="text-align:left">&#x6620;&#x5C04;&#x9375;</td>
    </tr>
    <tr>
      <td style="text-align:left">{rhs}</td>
      <td style="text-align:left">&#x6620;&#x5C04;&#x9375;&#x57F7;&#x884C;&#x7684;&#x529F;&#x80FD;</td>
    </tr>
    <tr>
      <td style="text-align:left">Leader</td>
      <td style="text-align:left">&#x6B64;&#x70BA;&#x8A2D;&#x5B9A;&#x9375;&#x503C;&#x7684;&#x8B8A;&#x6578;&#xFF0C;&#x9810;&#x8A2D;&#x70BA;
        \</td>
    </tr>
    <tr>
      <td style="text-align:left">silent</td>
      <td style="text-align:left">
        <p>&#x8981;&#x5728;&#x5B9A;&#x7FA9;&#x4E00;&#x500B;&#x6620;&#x5C04;&#x6642;&#x4E0D;&#x5728;&#x547D;&#x4EE4;&#x884C;&#x4E0A;&#x56DE;&#x986F;&#x8A72;&#x6620;&#x5C04;
          <br
          />&#x53EF;&#x4EE5;&#x4F7F;&#x7528; silent &#x4F5C;&#x70BA;&#x7B2C;&#x4E00;&#x500B;&#x53C3;&#x6578;</p>
        <p>&#x4F8B;&#x5982;&#xFF1A;</p>
        <p><code>:map &lt;silent&gt; ,h /Header&lt;CR&gt;</code>
        </p>
      </td>
    </tr>
  </tbody>
</table>## 設定 Leader

預設 leader 為 \

你可以更改 Leader 變數  
`:let mapleader = ","`

如上 Leader 變成 ,

使用 leader 範例  
`:map <Leader>a i`

輸入 \a 會變成 i   
假如 Leader 變數為 \  
i 為插入模式

## 設定遞迴映射語法

{cmd} {lhs} {rhs}

前面指定模式英文加上 map  
map, nmap, vmap...

舉例

`:imap a b`  
插入模式輸入 a 輸出 b

`:imap b a`  
插入模式輸入 b 輸出 a

因為遞迴的關係  
輸入 a 會輸出 b  
又因為輸入 b 會輸出 a  
造成無限循環，導致設定失敗  
這時就要用避免遞迴映射語法

## 設定避免遞迴映射語法

{cmd} {lhs} {rhs}

前面指定模式英文加上 noremap  
noremap, nnoremap, vnoremap...

舉例

`:inoremap a b`  
插入模式輸入 a 輸出 b

`:inoremap b a`  
插入模式輸入 b 輸出 a

因為避免遞迴的關係  
輸入 a 會輸出 b  
輸入 b 會輸出 a  
兩者不互相影響

## 刪除映射語法

{cmd} {lhs}

前面指定模式英文加上 unmap  
unmap, nunmap ,vunmap...

舉例

`:unnmap gq`  
刪除 gq 映射

## 常用指令

`:map`  
顯示映射指令表

`:h key-notation`  
查看按鍵英文名稱



