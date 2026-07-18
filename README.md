# 福生當鋪官方網站

福生當鋪的官方網站，提供店家介紹、服務項目、聯絡方式與營業時間等資訊。

- 網址：<https://fusheng-pawnshop.com>
- 店址：雲林縣斗六市大學路一段527號
- 電話：(05)5339997
- 營業時間：週一至週五 早上 9:00 – 晚上 6:00（週六、週日休息）

網站以 [Jekyll](https://jekyllrb.com/) 建置，基於 [minima](https://github.com/jekyll/minima) 佈景主題（3.0 開發版）修改而成，透過 GitHub Pages 部署。

## 網站頁面

| 頁面 | 檔案 | 網址 | 說明 |
| --- | --- | --- | --- |
| 首頁 | `index.md` | <https://fusheng-pawnshop.com/> | 形象首頁：主視覺、服務特點、服務項目、借款流程、立案證照 |
| 關於 | `about.md` | <https://fusheng-pawnshop.com/about/> | 店家介紹（合法當鋪、政府立案）與立案證照 |
| 服務特點及項目 | `business_type.md` | <https://fusheng-pawnshop.com/buinese_type/> | 服務特點、服務項目（汽車、機車、黃金金飾）、借款流程、準備資料 |
| 文章 | `_posts/` | — | 部落格文章 |

頁尾（`_includes/footer.html`）會顯示聯絡資訊、營業時間、Facebook 連結與 Google 地圖。

## 專案結構

```
.
├── _config.yml          # 網站設定：店名、電話、地址、營業時間開關、社群連結
├── _includes/           # 頁面片段（header、footer、head 等）
│   └── footer.html      # 自訂頁尾：聯絡資訊、營業時間、Google 地圖嵌入
├── _layouts/            # 頁面版型（default、home、page、post）
├── _posts/              # 部落格文章（檔名格式：YYYY-MM-DD-標題.md）
├── _sass/               # 佈景主題樣式（minima）；品牌樣式在 minima/custom-styles.scss
├── assets/              # 主題樣式進入點、社群 icon 與圖片（店面照、立案證照）
├── svg/                 # 服務特點與服務項目的圖示
├── CNAME                # GitHub Pages 自訂網域（fusheng-pawnshop.com）
├── sitemap.xml          # 搜尋引擎 sitemap
└── google*.html         # Google Search Console 驗證檔
```

## 修改網站內容

- **聯絡資訊／營業時間**：電話與地址在 `_config.yml` 的 `author` 區塊；營業時間的文字寫在 `_includes/footer.html`，可用 `_config.yml` 的 `businese_hours: true/false` 開關整個區塊。
- **服務項目**：編輯 `business_type.md`，圖示放在 `svg/` 目錄。
- **新增文章**：在 `_posts/` 新增 `YYYY-MM-DD-標題.md`，front matter 設定 `layout: post`。
- **社群連結**：`_config.yml` 的 `minima.social_links`（目前只啟用 Facebook）。
- **樣式調整**：全站樣式覆寫放在 `_sass/minima/custom-variables.scss` 與 `_sass/minima/custom-styles.scss`；`business_type` 頁面另有獨立的 `css/business_type.css`。

## 本機開發

需要 Ruby 與 Bundler。

```bash
bundle install
bundle exec jekyll serve   # 或執行 script/server
```

啟動後開啟 <http://localhost:4000> 預覽，修改檔案會自動重新產生頁面。

## 部署

推送到 `master` 分支後，GitHub Pages 會自動建置並發布至 `fusheng-pawnshop.com`（由 `CNAME` 檔指定網域）。

## 授權

佈景主題 minima 依 [MIT License](LICENSE.txt) 授權。
