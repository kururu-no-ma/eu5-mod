# 🏯 雲樺王國 — EU5 自訂國家 Mod

## 📦 安裝方法

1. 把整個 `yunhua_kingdom` 資料夾複製到：
   ```
   Documents/Paradox Interactive/Europa Universalis V/mod/
   ```

2. 開 Paradox Launcher → 建立或編輯 Playset → 把「Yunhua Kingdom」加進去 → Apply

3. 進遊戲選國家時搜尋 "Yunhua" 或看台灣北部（凱達格蘭）！

---

## 🎮 國家資訊

| 項目 | 設定 |
|------|------|
| 國家 Tag | YHW |
| 國名 | Yunhua（雲樺） |
| 首都 | ketagalan（凱達格蘭，北台灣） |
| 文化 | minnan_culture（閩南） |
| 宗教 | sanjiao（三教） |
| 政府 | 君主制 |
| 等級 | Duchy（公國） |
| 開國君主 | 呂雲樺（Lu Yunhua），23歲登基 |

---

## ⚠️ 如果遊戲報錯

最可能出問題的地方：

1. **`include = "confucian_monarchy"` 模板不存在**
   → 去原版 `game/main_menu/setup/templates/` 找可用的模板名稱替換
   → 檔案：`in_game/setup/start/99_yunhua.txt`

2. **`religion_definition = sanjiao` 的 key 不對**
   → 用 debug mode 把滑鼠移到台灣的省份，看宗教的 key 到底叫什麼
   → 檔案：`in_game/setup/countries/99_yunhua.txt` 和 `in_game/setup/start/99_yunhua.txt`

3. **角色定義語法不對**
   → 參考原版 `setup/start/` 裡其他國家的角色寫法
   → 檔案：`in_game/setup/start/99_yunhua.txt`

4. **Error log 位置**
   → `Documents/Paradox Interactive/Europa Universalis V/logs/error.log`

---

## 📁 檔案結構

```
yunhua_kingdom/
├── .metadata/
│   └── metadata.json              ← Mod 基本資訊
├── in_game/
│   ├── setup/
│   │   ├── countries/
│   │   │   └── 99_yunhua.txt      ← 國家定義（顏色、文化、宗教）
│   │   └── start/
│   │       └── 99_yunhua.txt      ← 起始狀態（省份、首都、君主）
│   ├── common/
│   │   └── advances/
│   │       └── yhw_advances.txt   ← 自訂科技樹（6 個 advance）
│   └── localization/
│       └── english/
│           └── yhw_l_english.yml  ← 英文文字
├── main_menu/
└── loading_screen/
```

---

## 🧠 自訂科技樹

| Advance | 時代 | 效果 |
|---------|------|------|
| Island Resilience | 傳統 | 駐軍 +15%, 堡壘防禦 +10% |
| Coastal Traders | 傳統 | 貿易價值 +10%, 海軍上限 +10% |
| Seafaring Tradition | 中世紀 | 海軍維護 -15%, 船隻耐久 +5% |
| Mountain Strongholds | 中世紀 | 防禦 +15%, 敵方消耗 +1 |
| Entrepôt of the East | 文藝復興 | 貿易力量 +15%, 商人 +1 |
| Island Unity | 文藝復興 | 穩定度 +10%, 叛亂 -1 |

---

## 🛠️ 想要更多？

- 加旗幟：放圖檔到對應的 flag 資料夾
- 加事件：在 `in_game/events/` 建 .txt 檔
- 加更多 advance：直接在 `yhw_advances.txt` 裡追加
- 換起始省份：用 debug mode 查新的 location key，改 `own_control_core` 和 `capital`
