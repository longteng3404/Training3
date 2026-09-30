# 心智圖簡報工具

用純文字大綱做心智圖、流程與文字雲，並直接播放成簡報。整個工具只有一個 `index.html`，不需要安裝。

## 放到 GitHub Pages

1. 在 GitHub 建立一個新的 repository（例如 `mindmap`）。
2. 把這個資料夾裡的檔案全部上傳（`index.html`、`.nojekyll`、`README.md`，其他檔案視需要）。
3. 到 repository 的 **Settings → Pages**：
   - Source 選 **Deploy from a branch**
   - Branch 選 **main**，資料夾選 **/ (root)**，按 **Save**
4. 等一兩分鐘，頁面上方會出現網址，例如 `https://你的帳號.github.io/mindmap/`。

> **注意：GitHub Pages 的網站是公開的**（只有 GitHub Enterprise Cloud 可以設成私人）。
> 請不要把公司內部的 `.txt` 內容、圖片放進這個 repository。

## 資料怎麼接上工具

工具本身不含任何資料，打開是空白的歡迎畫面。有三種方式帶入內容：

| 方式 | 做法 | 適合 |
|---|---|---|
| 開啟電腦裡的檔案 | 按「開啟 .txt 檔」或把檔案拖進視窗 | 平常編輯 |
| 分享連結（建議） | 工具列按「分享連結」，內容會壓縮後放進連結本身 | 貼到 Canva、寄給同事；內容不會存到任何伺服器 |
| 網站上的檔案 | 把 `.txt` 放進 repository，用 `?file=檔名.txt` 開啟 | 公開的範例或教學（內容會公開） |

網址參數：

- `#doc=…`：分享連結產生的內容（由工具自動產生，不用手寫）
- `?file=examples/範例.txt`：開啟網站上的檔案
- 加上 `present`（例如 `?file=examples/範例.txt&present`）：打開後直接準備進入簡報

## 在 Canva 簡報裡使用

Canva 只能嵌入它支援的服務，一般網頁不一定能直接嵌在投影片裡。建議做法：

1. 在工具按「分享連結」，複製「簡報連結」。
2. 在 Canva 選一個按鈕、圖片或文字 → 按 **連結**（鎖鏈圖示）→ 貼上。
3. 簡報時點一下，瀏覽器會打開工具，按「▶ 開始簡報」進入全螢幕。

內容修改後，要重新產生分享連結並更新 Canva 上的連結。

## 即時文字雲（QR code 互動）

需要另外部署一個 Google Apps Script 後台，程式碼在 `互動文字雲後台.gs`（工具的文字雲面板也有「複製後台程式碼」按鈕）。部署步驟寫在程式碼最上方的註解裡。
