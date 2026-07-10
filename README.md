# 函證整理工具

這是一個可部署到 GitHub Pages 的靜態網站版本。設計原則是「網站提供工具，客戶檔案留在使用者自己的瀏覽器」。

## 使用方式

1. 開啟 GitHub Pages 網址。
2. 選擇銀行函證 Excel 檔。
3. 在瀏覽器內完成整理與預覽。
4. 下載整理後的 Excel。

## 資料保密設計

- 不提供檔案上傳 API。
- 不使用後端伺服器接收客戶檔案。
- 不使用表單送出。
- 不呼叫外部分析、紀錄或錯誤回報服務。
- Excel 解析套件已放在 `assets/`，不依賴外部 CDN 載入。
- 頁面加入 Content Security Policy，禁止 `fetch` / XHR / WebSocket 等網路連線。

也就是說，GitHub Pages 只負責提供網頁工具；函證檔案由使用者自己的瀏覽器讀取與整理。

## GitHub Pages 發布建議

建議 repository 結構如下：

```text
index.html
assets/
  xlsx.full.min.js
  exceljs.min.js
README.md
```

GitHub Pages 設定：

- Source: Deploy from a branch
- Branch: `main`
- Folder: `/ (root)`

發布後，同仁只需要開啟 GitHub Pages 網址即可使用。

## 注意事項

目前版本主要處理 Excel 格式函證。若要處理 PDF，必須另外加入 PDF 文字抽取、表格辨識或 OCR 流程。
