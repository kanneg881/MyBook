# wget

## 介紹

非互動式檔案下載工具，可以下載網站，特色是可以遞迴下載

## 下載

mac os 系統可以使用 brew 套件管理器安裝  
`brew install wget`

{% embed url="https://www.gnu.org/software/wget/" %}

其他系統可以由官網下載檔案安裝

## 簡易說明

用法：wget \[選項\]... \[URL\]...

### 舉例

`$ wget -p -m -k -P ./web https://www.tenlong.com.tw`  
下載天瓏書局的網站，檔案存放在 web 資料夾

### 選項

-P 將檔案儲存到指定目錄

-k 將下載到的 HTML 或 CSS 連結對到本機檔案

-m 開啟 mirror 模式

-p 下載所有顯示網頁所需的檔案，例如圖片等

