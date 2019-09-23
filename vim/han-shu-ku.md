# 函數庫

`escape({string}, {chars})`  
轉義 string，chars 為要被轉義的字元

`getcmdtype()`  
取得當前命令行類型，例如查找 `/` 或 `?`

`submatch({nr}[, {list}])`  
只用於 `:substitute` 命令或 `substitute()` 函數中的表達式內。 返回匹配內容的第 {nr} 個子匹配。 {nr} 為 0 則返回整個匹配的內容



