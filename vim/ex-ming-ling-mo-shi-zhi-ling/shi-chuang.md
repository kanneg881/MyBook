# 視窗、標籤頁

| 命令 | 用途 |
| :--- | :--- |
| `:[N]new [++opt] [+cmd]` | 創建一個新視窗並且開始編輯一個空檔案 |
| `:[N]sp[lit] [++opt] [+cmd] [file]` | 水平切分當前視窗，新視窗載入 {file} |
| `:[N]vne[w] [++opt] [+cmd] [file]` | 與 `:new` 命令相似，但是它垂直分割視窗 |
| `:[N]vs[plit] [++opt] [+cmd] [file]` | 垂直切分當前視窗，新視窗載入 {file} |

### 關閉視窗

| 命令 | 用途 |
| :--- | :--- |
| `:clo[se]` | 關閉活動視窗 |
| `:on[ly]` | 只保留活動視窗，關閉其他所有視窗 |
| `:q[uit]` | 退出當前視窗。如果是最後的一個，退出 Vim。 |
| `:qa[ll]` | 關閉所有視窗並退出 Vim 除非存在修改過的緩衝區 |
| `:wq` | 先執行 :w 再執行 :q 儲存後離開 |
| `:wqa[ll]` | 先保存所有打開的檔案 再關閉所有視窗，並退出 vim |

## 標籤頁

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x547D;&#x4EE4;</th>
      <th style="text-align:left">&#x7528;&#x9014;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>:[count]tabe[dit] [++opt] [+cmd] {file}</code>
      </td>
      <td style="text-align:left">&#x6253;&#x958B;&#x65B0;&#x6A19;&#x7C64;&#x9801;&#x4E26;&#x7DE8;&#x8F2F; <code>{file}</code>
        <br
        />&#x5982;&#x679C;&#x7D66;&#x51FA; <code>[count]</code>
        <br />&#x65B0;&#x6A19;&#x7C64;&#x9801;&#x51FA;&#x73FE;&#x5728;&#x7B2C; <code>[count]</code> &#x500B;
        <br
        />&#x6A19;&#x7C64;&#x9801;&#x4E4B;&#x5F8C;&#xFF0C;&#x5426;&#x5247;&#x65B0;&#x6A19;&#x7C64;&#x9801;&#x51FA;&#x73FE;&#x5728;&#x7576;&#x524D;&#x9801;&#x4E4B;&#x5F8C;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>:tabc[lose][!]</code>
      </td>
      <td style="text-align:left">&#x95DC;&#x9589;&#x7576;&#x524D;&#x6A19;&#x7C64;&#x9801;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>:tabo[nly][!]</code>
      </td>
      <td style="text-align:left">&#x95DC;&#x9589;&#x6240;&#x6709;&#x5176;&#x5B83;&#x7684;&#x6A19;&#x7C64;&#x9801;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>:tabn[ext] {count}</code>
      </td>
      <td style="text-align:left">&#x8F49;&#x5230;&#x7B2C; <code>{count}</code> &#x500B;&#x6A19;&#x7C64;&#x9801;
        <br
        />&#x9996;&#x500B;&#x6A19;&#x7C64;&#x9801;&#x7DE8;&#x865F;&#x70BA;&#x4E00;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>:tabn[ext]</code>
      </td>
      <td style="text-align:left">&#x8F49;&#x5230;&#x4E0B;&#x4E00;&#x500B;&#x6A19;&#x7C64;&#x9801;
        <br />&#x6700;&#x5F8C;&#x4E00;&#x500B;&#x6A19;&#x7C64;&#x9801;&#x5247;&#x8FF4;&#x7E5E;&#x5230;&#x7B2C;&#x4E00;&#x500B;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>:tabp[revious]</code>
      </td>
      <td style="text-align:left">&#x8F49;&#x5230;&#x524D;&#x4E00;&#x500B;&#x6A19;&#x7C64;&#x9801;
        <br />&#x9996;&#x500B;&#x6A19;&#x7C64;&#x9801;&#x5247;&#x8FF4;&#x7E5E;&#x5230;&#x6700;&#x5F8C;&#x4E00;&#x500B;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>:tabm[ove] [N]</code>
      </td>
      <td style="text-align:left">
        <p>&#x628A;&#x7576;&#x524D;&#x6A19;&#x7C64;&#x9801;&#x79FB;&#x5230;
          <br />&#x7B2C; N &#x500B;&#x6A19;&#x7C64;&#x9801;&#x4E4B;&#x5F8C;</p>
        <p>0 &#x4F7F;&#x7576;&#x524D;&#x6A19;&#x7C64;&#x9801;&#x6210;&#x70BA;&#x9996;&#x500B;&#x6A19;&#x7C64;&#x9801;
          <br
          />&#x5982;&#x679C;&#x6C92;&#x6709; N &#x7576;&#x524D;&#x6A19;&#x7C64;&#x9801;&#x6210;&#x70BA;&#x6700;&#x5F8C;&#x4E00;&#x500B;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>:tab ba[ll]</code>
      </td>
      <td style="text-align:left">&#x5C07;&#x6240;&#x6709;&#x7DE9;&#x885D;&#x5340;&#x8B8A;&#x6210;&#x6A19;&#x7C64;&#x9801;</td>
    </tr>
  </tbody>
</table>



