# Contributing to taiwan-vegetarian-food-database

感謝您對本資料庫的興趣。本文件說明如何貢獻資料，以及哪些貢獻不會被接受。

## 資料來源要求 Data Source Requirements

所有貢獻的數據必須來自以下可信來源之一：

- **衛福部食藥署 TFND**（台灣食品成分資料庫）
- **USDA FoodData Central**
- 已發表的同行評審期刊論文（需附 PMID 或 DOI）
- **衛福部國人膳食營養素參考攝取量（DRIs）**

不接受：部落格、食品公司官網、未發表數據、個人估算值。

## 如何提交 How to Contribute

1. Fork 此 repository
2. 在對應 JSON 檔案中新增或修改項目
3. 確保每筆資料包含 `source` 欄位（包含具體來源名稱或 PMID）
4. 更新 `_meta.last_updated` 至今日日期（格式：YYYY-MM-DD）
5. 提交 Pull Request，說明資料來源

## 接受的貢獻 Accepted Contributions

- 新增台灣常見素食食材的營養數據（需有 TFND 或 USDA 數據支持）
- 修正現有數據的錯誤（需說明正確來源）
- 新增 `taiwan_note_zh` 說明台灣在地背景
- 補充缺乏的微量營養素數據（鐵、鈣、鋅等）
- 新增純素者常見的健康議題（如 B12、碘缺乏）的相關食物

## 不接受的貢獻 Not Accepted

以下類型的 Pull Request 將會被關閉，不予合併：

- **商業推廣內容**：連結到特定品牌保健食品、補充品或食品公司
- **未有來源的數據**：沒有 `source` 欄位或來源不可驗證
- **醫療建議**：宣稱特定食物可治療或預防疾病
- **誇大效果的描述**：使用「根治」、「神奇」等無科學依據的表述
- **SEO 填充內容**：重複堆砌關鍵字，無實質資訊
- **不相關食物**：非素食食物，或與台灣市場無關的食材

## 資料格式 Data Format

請參考 `data/schema.json` 了解各欄位的格式要求。

新增食物時，`id` 欄位使用小寫英文加連字號（kebab-case），例如：`firm-tofu`、`black-sesame`。

## 問題回報 Bug Reports

發現資料錯誤請開 GitHub Issue，說明：
1. 錯誤的欄位和數值
2. 正確數值及其來源（PMID 或 TFND 連結）

---

本資料庫不接受任何形式的贊助或付費置入內容。
