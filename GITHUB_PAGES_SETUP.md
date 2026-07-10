# GitHub Pages 發布步驟

## 建議設定

- Repository 名稱：`bank-confirmation-organizer`
- Visibility：若只是單純靜態工具，公開或私人皆可依事務所政策決定
- Pages source：Deploy from a branch
- Branch：`main`
- Folder：`/ (root)`

## 要上傳的檔案

請上傳 `github-pages-site` 資料夾內的所有內容到 repository 根目錄：

```text
index.html
README.md
GITHUB_PAGES_SETUP.md
.nojekyll
assets/
  xlsx.full.min.js
  exceljs.min.js
```

## 保密重點

這個版本不設計任何上傳功能。使用者選取函證 Excel 後，檔案內容只在自己的瀏覽器記憶體中被解析，整理後的 Excel 也由自己的瀏覽器產生下載。

頁面另外加入 Content Security Policy：

- 禁止對外網路連線
- 禁止表單送出
- 禁止外部圖片與物件載入
- Excel 套件改由本站 `assets/` 載入，不依賴外部 CDN

因此 GitHub Pages 只提供工具頁面，不保存客戶檔案。

## 發布後網址

若使用 GitHub Pages，網址通常會是：

```text
https://<GitHub帳號或組織>.github.io/bank-confirmation-organizer/
```
