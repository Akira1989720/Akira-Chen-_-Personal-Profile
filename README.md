[README.md](https://github.com/user-attachments/files/30150305/README.md)
# 陳家輝 個人網站 Chia-Huei Chen — Personal Site

議題溝通與專案執行 ／ Project Planner — Content, Engagement & Training

靜態網站，無需後端、資料庫或建置工具，可直接部署。

## 內容來源
所有文案以《陳家輝個人網站文案 v2.1 鎖定版》為唯一有效來源。
請勿放回 v1／v2 已刪除或未確認的內容（電話、地址、裝備類型、未驗證數字等）。

## 檔案結構
```
.
├─ index.html                 # 網站主檔（含 SEO/OG 標籤）
├─ styles.css                 # 全站樣式
├─ main.js                    # 導覽、scrollspy、展開、淡入
├─ favicon.svg                # 網站圖示（陳字 monogram）
├─ README.md
└─ assets/
   ├─ images/
   │  ├─ portrait.jpg          # 個人照（已置入）
   │  ├─ project-southtw.jpg   # 南台灣專案照（已置入）
   │  ├─ og-image.png          # 社群分享圖 1200×630（已產生）
   │  ├─ project-training.jpg  # ★ 待補：原創培訓現場照
   │  └─ project-mazu.jpg      # ★ 待補：原創繞境後勤照
   └─ resume/
      └─ resume.pdf            # ★ 待補：履歷 PDF
```
★ = 尚待提供

## 本機預覽
在此資料夾開一個簡易伺服器（避免 file:// 造成資源載入問題）：
```
python3 -m http.server 8080
```
瀏覽器打開 http://localhost:8080

## 部署 A：Cloudflare Pages（建議）
1. 建 GitHub repo，把本資料夾所有檔案 push 上去。
2. Cloudflare 儀表板 → Workers & Pages → Create → Pages → Connect to Git → 選這個 repo。
3. 建置設定：Framework preset 選 None；Build command 留空；Build output directory 填 /（根目錄）。
4. Deploy。完成後會得到 xxxx.pages.dev 網址。
5. 有自訂網域時：Pages → Custom domains → 綁定。
6. 綁好網域後，把 index.html 內 6 處 `YOUR-DOMAIN` 換成實際網域（canonical、og:url、og:image、twitter:image、schema url）。

## 部署 B：GitHub Pages（替代）
1. repo → Settings → Pages → Source 選 main 分支 / 根目錄 → Save。
2. 取得 username.github.io/repo 網址；同樣記得替換 YOUR-DOMAIN。

## 部署前檢查清單
- [ ] 置入 assets/resume/resume.pdf，並回報以便接上下載鈕
- [ ] 補 project-training.jpg 與 project-mazu.jpg（原創照或取得授權）
- [ ] 綁定網域後替換 6 處 YOUR-DOMAIN
- [ ] （選）內容管理後台 CMS：方案待決定，見下

## 內容管理後台（CMS）
本站為無建置流程的純靜態 HTML，Decap CMS 需搭配建置步驟才能即時反映文字修改。
建議兩選一（待你決定後於下一輪執行）：
- 方案 A：轉為 Astro + Decap CMS，取得真正的 /admin 圖形後台（可上傳圖片、改文字、雙語）。
- 方案 B：維持純靜態，文字修改直接改 index.html（最簡單，但需碰原始碼）。
