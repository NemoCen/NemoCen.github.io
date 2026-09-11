# NemoCen · Academic Homepage

**[中文版](https://nemocen.github.io/) · [English](https://nemocen.github.io/en/)**

依照 [luost26/academic-homepage](https://github.com/luost26/academic-homepage) 改成中英雙語的單頁個人學術網站。每種語言都有完整的關於我、履歷、研究與作品、獎項與榮譽，左上角可切換「中文／English」。切換時會保留網址中的區塊位置。

桌面版左側是個人資料卡，右側是各個內容區塊；手機版自動排列成單欄。兩種語言共用同一套版面，停用 JavaScript 仍可閱讀及切換語言。

## 修改文字內容

| 入口 | 修改內容 |
| --- | --- |
| **[編輯中文資料](https://github.com/NemoCen/NemoCen.github.io/edit/main/_data/profile.yml)** | 中文自介、學經歷、研究、獎項，以及共用照片、聯絡方式與履歷 PDF |
| **[Edit English content](https://github.com/NemoCen/NemoCen.github.io/edit/main/_data/profile_en.yml)** | English biography, positions, education, experience, research, and awards |

1. 開啟需要修改的語言檔案。
2. 修改引號內的文字，保留縮排、冒號與引號。
3. 按 **Commit changes**，提交到 **main**。
4. 等 GitHub Pages 更新完成，再重新整理網站。[查看更新進度](https://github.com/NemoCen/NemoCen.github.io/actions)

**中英文文字需要分別維護，不會自動翻譯。** 新增研究時，請在兩個檔案中以相同順序新增對應項目。姓名保留你自行填寫的拼法；中文姓名也可保留在英文頁面上。

| 欄位 | 內容 |
| --- | --- |
| `primary_name`、`secondary_name` | 主要姓名、第二姓名 |
| `navbar_name` | 頂部導覽列的名字，留空時沿用主要姓名 |
| `positions` | 職稱、學位、學校或單位 |
| `about` | 自介；每個 `-` 是一個段落 |
| `interests` | 研究方向 |
| `education` | 學校、系所、學位、年份 |
| `experience` | 單位、職稱、工作內容、年份 |
| `research` | 論文／專案、作者、期刊／會議、年份、摘要與連結 |
| `awards` | 獎項名稱、頒發單位、年份 |

增加資料時，複製該區塊中一整組 `-` 開頭的項目，再修改內容。清空整個清單可寫成 `awards: []`。以 `#` 開頭的行是註解，不會顯示。尚未填寫的獎項提示文字可以自行刪除或替換。

## 上傳照片

1. 準備真正的 JPG、PNG 或 WebP 圖片，例如 `personalimage.jpg`。
2. 開啟 **[上傳檔案](https://github.com/NemoCen/NemoCen.github.io/upload/main)**，按 **Choose your files** 選擇照片，或將照片拖入上傳區。
3. 按 **Commit changes** 儲存。若上傳同名檔案，會替換原有檔案。
4. 回到中文資料，將路徑填在 `portrait_url`：

```yaml
portrait_url: "/personalimage.jpg"
```

**請使用 Add file → Upload files 上傳圖片。Create new file 是建立文字檔；把文字檔命名為 `.jpg` 並不會變成照片。** 也不要只把 `.png` 的副檔名改為 `.jpg`。

路徑、檔名、副檔名及大小寫都必須一致。例如上傳 `photo.png`，就填 `"/photo.png"`。可在 GitHub 打開該檔案確認是否能看到圖片預覽。

若 GitHub 無法預覽圖片，請確認檔案中有真正的圖片內容。空白文字檔需要上傳真正的照片替換。圖片未填寫或載入失敗時，網站會顯示照片預留位置。

**照片只需上傳一次，中英文頁面都使用中文資料中的 `portrait_url`。**

## 履歷、研究圖片與連結

- **履歷 PDF**：用同一個上傳入口上傳 PDF，在中文資料填 `cv_link: "/cv.pdf"`。兩種語言共用這個連結。
- **研究圖片**：上傳圖片後，在中文資料對應研究的 `cover` 填入路徑；英文版 `cover` 留空時會使用相同位置的中文研究圖片。若需要不同的英文圖片，可在英文資料的 `cover` 另填路徑。
- **聯絡方式**：`email`、`github`、`gscholar`、`orcid` 只需在中文資料填寫。留空的連結不會顯示。Google Scholar 填完整個人頁網址；ORCID 填編號。
- **論文與程式連結**：英文 `links` 留空時，會共用相同位置的中文研究連結；也可在英文資料另填英文版連結與標籤。

每筆研究的 `links: []` 可改成：

```yaml
    links:
      - name: "Paper"
        url: "https://你的論文網址"
      - name: "Code"
        url: "https://github.com/你的帳號/專案"
```

研究項目會依照檔案中的順序顯示，將最新的放在上方即可。

## 網站結構

- `_data/profile.yml`：中文個人資料與共用圖片、聯絡連結。
- `_data/profile_en.yml`：英文個人資料。
- `_data/ui.yml`：中英文介面標籤。
- `_layouts/academic.html`：兩種語言共用的版面、樣式與導覽功能。
- `index.html`、`en/index.html`：中文與英文入口。
- `_config.yml`：GitHub Pages 的 Jekyll 設定。

沿用 `main` 分支根目錄發布，不需要自行安裝工具或改部署設定。網站無額外前端套件、追蹤程式或第三方字型載入。

## 模板來源

Based on **[academic-homepage](https://github.com/luost26/academic-homepage)** by Shitong Luo, under the MIT License. 原始授權保留於 [LICENSE](LICENSE)。
