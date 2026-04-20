# 台灣素食營養資料庫 Taiwan Vegetarian Food Nutrition Database

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Data Source](https://img.shields.io/badge/來源-衛福部%20TFND%20%2F%20PMID-blue)](https://consumer.fda.gov.tw/Food/TFND.aspx)

## 為什麼建立這個

台灣素食人口約佔總人口 10–13%（約 250–300 萬人），是亞洲素食比例最高的地區之一。
然而，開發者在製作素食健康工具時，面臨以下困境：

1. **植物性蛋白質數據缺乏台灣在地食材**：豆腐、天貝、毛豆等台灣常見素食蛋白質來源，在西方資料庫的份量描述不符合台灣飲食習慣
2. **營養缺口風險缺乏結構化資料**：B12、鐵、鋅、Omega-3 等素食常見缺口，需要整合台灣衛福部 DRIs 與國際實證

本資料庫提供：
- 台灣常見植物性蛋白質食物（每 100g 含量）
- 素食主食熱量與巨量營養素
- 素食者常見 6 大營養缺口（含衛福部建議攝取量與食物來源）

---

## 資料檔案

| 檔案 | 內容 |
|------|------|
| `data/plant-proteins.json` | 台灣植物性蛋白質食物（豆類、豆製品、穀物、堅果） |
| `data/vegan-staples.json` | 素食主食熱量與巨量營養素（含素食便當常見配菜） |
| `data/nutrient-gaps.json` | 素食/純素 6 大營養缺口（B12、鐵、鋅、Omega-3、鈣、維生素D） |
| `data/schema.json` | JSON Schema（draft-07）欄位定義 |

---

## 快速使用

```js
import plantProteins from './data/plant-proteins.json'

// 找出蛋白質含量 > 15g/100g 的植物性食物
const highProtein = plantProteins.filter(f => f.protein_g_per_100g >= 15)
console.log(highProtein.map(f => f.name_zh))
// → ['天貝', '麵筋（烤麩）', '南瓜籽', '藜麥（乾）', ...]
```

---

## 素食營養缺口速查

| 營養素 | 缺口風險 | 台灣 DRI | 最佳植物來源 |
|--------|---------|---------|------------|
| 維生素 B12 | 純素：極高 | 2.4 μg/day | **無**（需補充劑）|
| 鐵（非血鐵）| 中等 | 男 10mg/女 15mg | 黑豆、紅莧菜、南瓜籽 |
| 鋅 | 中等 | 男 15mg/女 12mg | 南瓜籽、腰果、藜麥 |
| Omega-3（EPA/DHA）| 純素：高 | — | **無直接來源**（ALA 轉換率 < 5%）|
| 鈣 | 純素：中等 | 1000 mg/day | 板豆腐、黑芝麻、莧菜 |
| 維生素 D | 全素食：中等 | 10 μg/day | 日曬香菇（有限）|

---

## 延伸資源

台灣植物性飲食與體重管理完整指南：[metabolab.tw/topics/nutrition](https://metabolab.tw/topics/nutrition)

---

## 健康免責聲明

本資料庫數值僅供參考與教育用途，不構成醫療或營養建議。純素飲食者建議定期監測 B12、鐵、維生素 D 等指標，並諮詢合格醫師或營養師。

---

## 資料來源

- 衛福部食藥署台灣食品營養成分資料庫（TFND）：https://consumer.fda.gov.tw/Food/TFND.aspx
- 衛福部國民健康署. 國人膳食營養素參考攝取量（DRIs）第八版（2020）
- Melina V, Craig W, Levin S. (2016). Position of the Academy of Nutrition and Dietetics: Vegetarian Diets. *J Acad Nutr Diet*, 116(12):1970-1980. PMID: 27886704
- Pawlak R et al. (2013). How prevalent is vitamin B12 deficiency among vegetarians? *Nutr Rev*, 71(2):110-117. PMID: 23356638
- USDA FoodData Central：https://fdc.nal.usda.gov
