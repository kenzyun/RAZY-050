# Tesla BT Control — URL Hash 指令對照表

## 使用方式

在 URL 後加上 `#指令` 即可讓頁面自動連接藍牙、登入並執行對應動作。

```
https://kenzyun.github.io/RAZY-050/#door-rf
```

執行流程：
1. 頁面載入，讀取 hash 指令
2. 自動連接上次配對的 KLOVEF-System（免選擇）
3. 自動送出已儲存密碼登入（免輸入）
4. 登入成功後立即執行指令
5. 顯示 Toast 結果，1.5 秒後自動關閉分頁

> 首次使用前須至少手動開啟一次 index.html、完成配對並登入，讓瀏覽器記住設備與密碼。

---

## 指令對照表

| 功能 | Hash |
|------|------|
| 車輛上鎖 | `#lock` |
| 車輛開鎖 | `#unlock` |
| 打開右前門 | `#door-rf` |
| 打開右後門 | `#door-rr` |
| 打開左後門 | `#door-lr` |
| 開後備箱 | `#trunk-open` |
| 關後備箱 | `#trunk-close` |
| 開前備箱 | `#frunk-open` |
| 關前備箱 | `#frunk-close` |
| 打開手套箱 | `#glove` |
| 開充電蓋板 | `#charge-open` |
| 關充電蓋板 | `#charge-close` |
| 遠光爆閃 | `#flash-hi` |
| 脈衝喇叭 | `#horn-pulse` |
| 年檢模式：開 | `#annual-on` |
| 年檢模式：關 | `#annual-off` |

---

## Android 自動化設定（Macrodroid）

1. 安裝 [Macrodroid](https://play.google.com/store/apps/details?id=com.arlosoft.macrodroid)
2. 新增 Macro：
   - **Trigger** → Assistant Trigger（或 Voice Recognition）→ 輸入觸發語句，例如「打開右前門」
   - **Action** → Applications → Open Website → 填入對應 URL，例如：
     ```
     https://kenzyun.github.io/RAZY-050/#door-rf
     ```
   - 選擇以 Chrome 開啟
3. 儲存 Macro，之後說出觸發語句即可自動執行

每個指令建立一個 Macro，或使用 Macrodroid 的變數功能讓單一 Macro 處理多個指令。
