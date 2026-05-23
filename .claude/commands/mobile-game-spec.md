你正在為「親子災後保衛營」開發一個手機網頁遊戲關卡。請遵守以下所有規格。

## 技術限制
- 純 HTML/CSS/JS，單一 index.html，零 build tool
- Tailwind CSS via CDN
- 不依賴外部 API 或後端

## 版面結構
- max-width: 430px，margin: 0 auto
- 背景色：gray-900（#111827）
- 字體：Noto Sans TC 優先，fallback system-ui

## 三層固定結構（每個關卡都要有）
1. **Fixed header**（`fixed top-0 w-full`，z-20）：顯示關卡名稱、即時數值或進度條
2. **可捲動內容區**（`pt-[header高度] pb-[CTA高度]`）：劇情說明、選項卡片
3. **Fixed CTA button**（`fixed bottom-0 w-full`，z-20）：主要操作，全寬，h-14，font-bold

## 互動規範
- 所有玩家互動只用**按鈕選單**，不允許文字輸入
- 按鈕最小高度 48px（確保行動裝置 tap target 足夠大）
- 選項卡片樣式：`rounded-2xl border bg-gray-800 p-4 active:scale-95 transition-transform`
- 選中狀態加 `ring-2 ring-[accent色]`

## 字體大小規範
- 關卡主標題：`text-xl font-bold`
- 劇情說明：`text-sm text-gray-400 leading-relaxed`
- 關鍵數值（血量/預算等）：`text-2xl font-black`
- 標籤/單位：`text-xs text-gray-500`

## 顏色主題（accent color 依關卡）
| 關卡 | 顏色 | Tailwind |
|------|------|----------|
| 光之呼吸 | #FCD34D | yellow-300 |
| 水之呼吸 | #22D3EE | cyan-400 |
| 炎之呼吸 | #FB923C | orange-400 |
| 雷之呼吸 | #FACC15 | yellow-400 |
| 風之呼吸 | #7DD3FC | sky-300 |
| 土之呼吸 | #FBBF24 | amber-400 |

## 難度設計原則
- 目標受眾：10 歲以下兒童 + 家長一起玩
- 所有文字說明簡短清楚，不超過 2 行
- 錯誤不用「死亡」，改用受傷／困住／走散等可逆狀態
- 每關 5 回合左右，總時間控制在 3–5 分鐘

## 結尾行為
- 「再試一次」按鈕一律用 `location.reload()`，不導回其他頁面
- 結尾畫面要有知識解說（正確答案的理由）

## 檔案命名規則
每個關卡放在 `games/[關卡英文名]/index.html`，例如：
- games/light/index.html
- games/water/index.html
