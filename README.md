# 我的投資儀表板 📈

一個極簡的靜態網頁，作為 **GitHub Pages 前端入口**，透過全螢幕 `<iframe>` 將實際應用程式轉址至 **Google Apps Script (GAS)** 所部署的網頁服務。

## 🗂️ 架構說明

```
使用者瀏覽 GitHub Pages URL
        ↓
   index.html（靜態網頁）
        ↓  全螢幕 iframe 嵌入
Google Apps Script Web App
（試算表資料 / 投資儀表板邏輯）
```

GitHub Pages 提供一個固定、乾淨的網址，實際的儀表板內容與資料處理邏輯全部由 Google Apps Script 負責。當 GAS 部署網址有異動時，只需修改 `index.html` 中的 `iframe src` 即可，無需更改對外分享的連結。

## 📁 專案結構

```
stock/
├── index.html   # 靜態前端入口，嵌入 GAS 網頁
└── README.md
```

## 🔧 index.html 說明

- 移除 `body` 預設邊距，讓 iframe 完整填滿整個視窗
- 禁用外層捲軸（`overflow: hidden`），避免出現雙重捲軸
- iframe 以絕對定位撐滿 100% 寬高，模擬原生 App 體驗
