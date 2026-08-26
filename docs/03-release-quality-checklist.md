# 階段 3：上線品質檢查紀錄

> 檢查日期：2026-08-26

## 已完成

- [x] 全站共用 `lang="zh-Hant"`、viewport 與內容描述。
- [x] 每頁依自身標題與摘要產生 title、description、canonical、Open Graph 與 X metadata。
- [x] 產生 `sitemap-index.xml` 及 18 條可索引的正式頁面 URL。
- [x] 建立 `robots.txt`，允許索引並指向 sitemap。
- [x] 提供跳至主要內容連結、鍵盤焦點樣式、具名稱的主要導覽與可展開提示詞。
- [x] 小螢幕下，導覽、Part 卡片與方法卡切換為單欄；內容表格保留可閱讀的欄位結構。
- [x] Pagefind 搜尋索引僅索引主要內容區塊。
- [x] 兩個 GitHub 延伸資源連結均於 2026-08-26 確認可存取。
- [x] `npm run build` 完成；輸出 19 個靜態頁面與 Pagefind 索引。

## 發布前需確認

- [ ] Cloudflare Pages 專案名稱若不是 `pm-is-life-ai-ost`，需設定 `PUBLIC_SITE_URL` 為實際 production 網址，再重新建置。
- [ ] 以 Cloudflare Preview URL 檢查桌面、平板與手機的實際字級、表格捲動及提示詞複製操作。
- [ ] 按內容修訂規格書逐段校對每章的完整提示詞、圖解與延伸資源敘述。
- [ ] 正式發布前再次檢查所有外部 AI 工具與 GitHub 連結。

