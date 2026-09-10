# NemoCen · Academic Homepage

**[瀏覽網站](https://nemocen.github.io/) · [直接編輯個人資料](https://github.com/NemoCen/NemoCen.github.io/edit/main/_data/profile.yml)**

依照 [luost26/academic-homepage](https://github.com/luost26/academic-homepage) 改成單頁個人學術網站。桌面版左側是個人資料卡，右側依序為 About Me、Résumé、Research & Publications、Honors & Awards；手機版自動排列成單欄。

導覽全部是同一頁內的區塊跳轉，沒有獨立的履歷、研究、獎項頁面。

## 只要編輯一個檔案

你的文字內容集中在 **[`_data/profile.yml`](https://github.com/NemoCen/NemoCen.github.io/edit/main/_data/profile.yml)**。

1. 開啟上面的「直接編輯個人資料」。
2. 將引號內的提示文字換成自己的資料，保留縮排、冒號與引號。
3. 按 **Commit changes**，提交到 **main**。
4. 等 GitHub Pages 更新完成，再重新整理網站。[查看更新進度](https://github.com/NemoCen/NemoCen.github.io/actions)

| 欄位 | 內容 |
| --- | --- |
| `primary_name`、`secondary_name` | 英文名／主要姓名、中文名／第二姓名 |
| `navbar_name` | 頂部導覽列的名字，留空會自動沿用主要姓名 |
| `positions` | 職稱、學位、學校或單位 |
| `about` | 自介；每個 `-` 是一個段落 |
| `interests` | 研究方向 |
| `education` | 學校、系所、學位、年份 |
| `experience` | 單位、職稱、工作內容、年份 |
| `research` | 論文／專案、作者、期刊／會議、年份、摘要與連結 |
| `awards` | 獎項名稱、頒發單位、年份 |

增加一筆學歷、研究或獎項：複製該區塊中一整組 `-` 開頭的項目，再修改內容。刪除不需要的那一整組即可減少項目。清空整個清單可寫成 `awards: []` 這樣的格式。

目前的學校、職稱、研究與獎項都是讓你自行填入的提示文字，沒有放入其他人的個人資料或學術成果。

## 放上照片和履歷 PDF

- **個人照片**：將檔案上傳到 網站根目錄，再將 `portrait_url` 設成例如 `"/portrait.jpg"`。
- **研究圖片**：同樣上傳到 網站根目錄，在該筆研究的 `cover` 填路徑。
- **履歷 PDF**：將檔案上傳到 網站根目錄，再將 `cv_link` 設成例如 `"/cv.pdf"`。

路徑與檔名大小寫需要一致，建議使用英文檔名。未提供照片時會保留照片位置；未填入 PDF 路徑時不顯示下載連結。

## 聯絡方式與研究連結

`email`、`gscholar`、`orcid` 留空就不顯示。Google Scholar 請填完整個人頁網址；ORCID 填編號即可。

每筆研究的 `links: []` 可改成下面的格式，將提示網址換成你的真實網址：

```yaml
    links:
      - name: "Paper"
        url: "https://你的論文網址"
      - name: "Code"
        url: "https://github.com/你的帳號/專案"
```

研究項目會依照檔案中的順序顯示，將最新的放在上方即可。

## 網站結構

- `_data/profile.yml`：你平常需要修改的個人資料。
- `index.html`：單頁內容、桌面／手機／列印樣式，以及導覽提示。停用 JavaScript 仍可閱讀所有內容。
- `_config.yml`：GitHub Pages 的 Jekyll 設定。

沿用 `main` 分支根目錄發布，不需要自行安裝工具或改部署設定。網站無額外前端套件、追蹤程式或第三方字型載入。

## 模板來源

Based on **[academic-homepage](https://github.com/luost26/academic-homepage)** by Shitong Luo, under the MIT License. 原始授權保留於 [LICENSE](LICENSE)；此版本針對單頁內容、集中填寫資料、手機閱讀與無額外套件的使用方式作了調整。
