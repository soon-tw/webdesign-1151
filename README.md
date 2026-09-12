# 上課簡報

互動式網頁設計（勤益科大進修部 115-1）上課簡報。

## 這是什麼

本目錄是**發佈產物**，由 `output/簡報建置/publish_slides.py` 從 `docs/02_簡報/` 產生。
內容主軸在 `docs/02_簡報/`，本目錄可隨時刪除重建，請勿在此手改內容。

## 目錄結構

```
index.html                簡報總覽
assets/deck-fonts.css     共用字型（base64 woff2 子集，離線可用）
assets/deck-site.css      網站與「回總覽」樣式
<slug>/index.html         各週簡報
```

`deck-fonts.css` 由所有簡報共用，瀏覽器只需下載一次；
字型以 base64 內嵌，因此**整包下載後直接雙擊開啟也能正確顯示**，不依賴網路。

## 部署到 GitHub Pages

```bash
# 1. 首次：建立遠端並推上去
cd docs/slides
git init -b main
git add -A && git commit -m "init: 上課簡報網站"
git remote add origin git@github.com:<你的帳號>/<repo>.git
git push -u origin main

# 2. 在 GitHub repo → Settings → Pages
#    Source 選 "Deploy from a branch"
#    Branch 選 main，資料夾選 / (root) → Save
```

網址會是 `https://<你的帳號>.github.io/<repo>/`。

## 更新簡報

```bash
bash scripts/publish-slides.sh          # 重新產生網站
bash scripts/publish-slides.sh --push   # 重新產生並推送
```

## 新增一週

在 `output/簡報建置/slides.json` 的 `slides` 陣列加一筆（slug 用 ASCII），再跑上方指令。
