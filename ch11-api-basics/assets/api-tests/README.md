# CH11 API 測試附件

全部附件皆於 **2026-11-14** 實跑通過；不含任何真實金鑰。

| 檔案 | 用途 | 怎麼用 |
| --- | --- | --- |
| `youbike.http` | 第 31 頁：YouBike 站點列表＋練 POST | VS Code 安裝「REST Client」，點請求上方的 Send Request |
| `status-codes.http` | 第 14–19 頁：親手看到 200～503 | 同上；httpbin 會回傳網址指定的狀態碼 |
| `posts-rest.http` | 第 22–26 頁：RESTful 五個請求、404、空陣列、分頁 | 同上；JSONPlaceholder 寫入為模擬，不會真的保存 |
| `bruno/YouBike/` | 第 35–39 頁：Bruno 集合（4 個請求、10 個斷言、1 個測試） | Bruno → Open Collection → 選 `bruno/YouBike` 資料夾；右上角選 `dev` 環境 |

## 驗證紀錄

- Bruno：`cd bruno/YouBike && npx @usebruno/cli@4.3.0 run --env dev` → 4 requests passed、Assertions 10/10、Tests 1/1。
- `.http`：以 httpyac CLI（與 REST Client 語法相容）`send --all` → 2＋10＋9 個請求全部送出成功；狀態碼另以 curl 逐一確認。
- `environments/dev.bru` 的 `apiKey` 只是示範 Secret 的寫法，YouBike 不需要金鑰；值不會寫進檔案。
