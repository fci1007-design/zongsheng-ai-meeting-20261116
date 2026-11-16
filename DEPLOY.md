# 部署紀錄

- 更新時間：2026-11-16 20:22:04 +0800（Asia/Taipei）
- 目標環境：GitHub Pages（公開靜態網站）
- GitHub： https://github.com/fci1007-design/zongsheng-ai-meeting-20261116
- 網站： https://fci1007-design.github.io/zongsheng-ai-meeting-20261116/
- 目標分支／目錄：`main` / 根目錄
- 必要環境變數：無。部署沿用本機 GitHub CLI 登入；不在儲存庫保存憑證。
- 目前狀態：已發布，Pages 建置成功且線上 HTTP 200、內容一致性與瀏覽器實測通過。

## 驗證

- HTML 結構：7 項會議共識、7 項行動、表格僅 2 欄；錨點有效，指定刪除內容未出現。
- 真實 Chromium／Playwright：320、390、768、1024、1440px 各搭配 18、21、24px 字級，15 組全部無水平溢出；各組維持 7 項共識及 7 項行動。
- 字級重新載入後保留；導覽及瀏覽器返回有效；行動標題未被固定工具列遮擋。
- 列印按鈕觸發 `window.print`；列印媒體模式隱藏工具列、保留表格。未實際輸出 PDF 或紙本。
- 已目視檢查桌機整體畫面及手機行動卡片；修正 favicon 404 後重新載入無瀏覽器 console error 或 page error。
- 易裝修官方連結 https://www.ezid.com.tw/ 回應 HTTP 200。

## 發布歷程

- 2026-11-16 19:43:01 +0800：本機靜態頁與跨尺寸驗證完成，準備初次推送。

- 2026-11-16 19:43:53 +0800：初版 commit `2d869d9` 已推送至公開 GitHub 儲存庫；Pages 已建立，來源 `main` / `/`，HTTPS 開啟。等待建置及線上實測。

- 2026-11-16 19:45:09 +0800：Pages 初版 `2d869d9eb2e6a7f88c1ab4146bcab282f754cbdf` 建置狀態 `built`，公開網址 HTTP 200。線上 HTML 與本機逐 byte 相等，SHA-256 `62b452c22a0f1d9c8a1d8eb9476ee39e62260a58ddbc93a46f410e8caa20941c`。線上 390/1440px 特大字無水平溢出、7 項共識、7 項行動、2 欄、分工及刪除項目皆正確，無 page error。更新部署與交接文件。

## 後續查驗

```bash
gh api repos/fci1007-design/zongsheng-ai-meeting-20261116/pages/builds/latest
curl -I https://fci1007-design.github.io/zongsheng-ai-meeting-20261116/
git status --short --branch
git log -1 --oneline
```

重新部署：修改 `index.html`，跨尺寸驗證後提交並 `git push origin main`，確認 Pages 建置成功及公開內容正確，再更新本紀錄。

## 內容增補與分工校正（2026-11-16 20:20:25 +0800）

- 變更：共識由7短段落增補為23段；影音納入本期；標章資料僅總盛提供；影音由Sean提供經驗、總監評估技術；公司正名妍發科技。手機流程圖配合四階段調為兩欄。
- 本機驗證：7項共識／23段／7項行動／2欄及各項內容修正通過；15組寬度×字級無溢出，閱讀工具與列印CSS檢查通過，桌機／手機已目視。
- 環境：GitHub Pages原網址、main根目錄、必要環境變數無，與原部署相同。
- 狀態：已發布並通過線上驗證；內容 commit `052a2ac385b17ae93cc101f76ea8732f45c9f196` 已推送，Pages 狀態 built。

- 2026-11-16 20:22:04 +0800：增補版 `052a2ac385b17ae93cc101f76ea8732f45c9f196` 已發布。公開網址 HTTP 200，線上HTML與本機逐byte一致（SHA-256 `442dd0b98ce6f6abafd8483c9a478011a939fc255074abbdae17e29fcff9f71e`）；線上瀏覽器核對7主題23段、7項行動2欄、影音本期納入、妍發科技、標章僅總盛及影音Sean／總監分工全部通過。390/1440px特大字無溢出。本機預覽已停止；本次另保存部署與交接文件。
