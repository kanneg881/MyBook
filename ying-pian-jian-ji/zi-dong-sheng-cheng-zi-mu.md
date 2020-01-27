# 自動生成字幕

## 介紹

在 Youtube 和 Facebook 字幕可以用 srt 格式檔  
使用這個插件，影片可以自動生成字幕

## 下載

{% embed url="https://github.com/agermanidis/autosub" %}

## 簡易說明

1. 安裝 ffmpeg
2. 安裝 autosub

### 安裝 ffmpeg

`$ brew install ffmpeg`  
比較方便的做法是 brew 安裝

### 安裝 autosub

`$ pip install autosub`  
要注意權限的問題

`$ sudo pip install autosub`  
權限不足就用 sudo

### 常用參數

| 參數 | 說明 |
| :--- | :--- |
| -h, --help | 顯示幫助訊息並離開 |
| -o, --output | 輸出字幕檔的路徑（預設字幕保存與來源影片相同的目錄和名稱） |
| -F, --format | 目標字幕格式 |
| -S, --src-language | 源影片中說話的語言 |
| -D, --dst-language | 字幕所需的語言 |
| --list-formats | 列出所有可用的字幕格式 |
| --list-languages | 列出所有可用的源/目標語言 |

### 示範

`$ autosub -F srt -S zh_TW -D zh_TW path/to/file`  
生成 srt 源影片語言為繁體中文，輸出為繁體中文  
檔案在 path/to/file



  




