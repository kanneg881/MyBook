# 視窗、標籤頁、緩衝區

## 視窗

| 命令 | 用途 |
| :--- | :--- |
| `<Ctrl-w>s` | 水平切分當前視窗，新視窗顯示當前緩衝區 |
| `<Ctrl-w>v` | 垂直切分當前視窗，新視窗顯示當前緩衝區 |

### 在視窗切換

| 命令 | 用途 |
| :--- | :--- |
| `<Ctrl-w>w` | 視窗循環切換 |
| `<Ctrl-w>h` | 切換到左邊視窗 |
| `<Ctrl-w>j` | 切換到下面視窗 |
| `<Ctrl-w>k` | 切換到上面視窗 |
| `<Ctrl-w>l` | 切換到右邊視窗 |

### 移動視窗

| 命令 | 用途 |
| :--- | :--- |
| `<Ctrl-w>H` | 移動到最左邊視窗 |
| `<Ctrl-w>J` | 移動到最下面視窗 |
| `<Ctrl-w>K` | 移動到最上面視窗 |
| `<Ctrl-w>L` | 移動到最右邊視窗 |
| `<Ctrl-w>R` | 當前行或列，向左或向上移動 |
| `<Ctrl-w>r` | 當前行或列，向右或向下移動 |
| `<Ctrl-w>x` | 當前視窗與下一個視窗交換 如果是最後一個則與前一個交換 |

第二個按鍵可以按住 `<Ctrl>` 不放  
像 `<Ctrl-w><Ctrl-w>` 等同於 `<Ctrl-w>w`

### 關閉視窗

| 命令 | 用途 |
| :--- | :--- |
| `<Ctrl-w>c` | 關閉活動視窗 |
| `<Ctrl-w>o` | 只保留活動視窗，關閉其他所有視窗 |
| `<Ctrl-w>q` | 關閉活動視窗 |

### 改變窗口大小和重新排列視窗

| 命令 | 用途 |
| :--- | :--- |
| `<Ctrl-w>+` | 高度增加一行 |
| `<Ctrl-w>-` | 高度減少一行 |
| `<Ctrl-w>>` | 寬度增加一行 |
| `<Ctrl-w><` | 寬度減少一行 |
| `<Ctrl-w>=` | 使所有視窗等寬、等高 |
| `<Ctrl-w>_` | 最大化活動視窗高度 |
| `<Ctrl-w>|` | 最大化活動視窗寬度 |
| `[N]<Ctrl-w>_` | 把活動視窗高度設為 \[N\] 行 |
| `[N]<Ctrl-w>|` | 把活動視窗寬度設為 \[N\] 列 |

## 標籤頁

| 命令 | 用途 |
| :--- | :--- |
| `<Ctrl-w>T` | 把當前窗口移到一個新的標籤頁上 |
| `{count}gt` | 轉到第 `{count}` 個標籤頁 首個標籤頁編號為一 |
| `gt` | 轉到下一個標籤頁 最後一個標籤頁則迴繞到第一個 |
| `gT` | 轉到前一個標籤頁 首個標籤頁則迴繞到最後一個 |

## 緩衝區

`<Ctrl-^>`  
切換到之前的緩衝區

