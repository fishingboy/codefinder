# codefinder

[![Packagist Version](https://img.shields.io/packagist/v/fishingboy/codefinder.svg)](https://packagist.org/packages/fishingboy/codefinder)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

[English](README.md) | 繁體中文

codefinder 是一個輕量的 PHP 執行階段檢查工具。載入後，它會在請求結束時輸出已 include 的 PHP 檔案清單，並提供簡單的搜尋表單，讓你在這些檔案中搜尋關鍵字。

## 需求

- PHP 5.3 或更新版本

## 安裝

使用 Composer 安裝：

```bash
composer require fishingboy/codefinder
```

## 使用方式

在需要檢查的請求中載入 `code_finder.php`：

```php
require_once __DIR__ . '/vendor/fishingboy/codefinder/code_finder.php';
```

請求結束時，codefinder 會在頁面後方附加檢查面板。未輸入關鍵字時，會顯示 `get_included_files()` 回傳的所有檔案；輸入關鍵字後，會搜尋已 include 檔案的路徑與檔案內容，並顯示符合的檔名與行號內容。

搜尋表單提供不分大小寫搜尋選項。

## 注意事項

- 建議只在本機開發或受控的除錯環境使用。
- 不要在正式環境輸出中啟用，因為它可能暴露檔案路徑、原始碼、請求資料與其他敏感資訊。
- 這個工具會直接將 HTML 寫入 response output。

## 授權

本專案採用 [MIT License](LICENSE) 授權。
