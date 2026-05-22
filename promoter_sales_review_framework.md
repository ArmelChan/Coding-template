# Promoter Sales Review 與 Incentive Game 結果對比框架

> **用途**：供每週/每期重複使用之零售管理層內部匯報模板。  
> **注意**：以下「Demo 匯報」為 **SAMPLE DATA ONLY / NOT FINAL RESULT**，僅示範格式與表達方式。

## 1) 下星期一請提供的資料欄位模板（Excel copy & paste 文字版）

| 欄位名稱 | 用途 | 是否必要 |
|---|---|---|
| campaign_period | 定義分析期間（例如 2026-05-01~2026-05-31） | 必要 |
| promoter_name | 個別 Promoter 身份識別 | 必要 |
| promoter_id | 去重及跨期追蹤（同名不同人） | 建議 |
| store | 門店表現對比與資源分配分析 | 必要 |
| region | 區域聚合分析（North/South 等） | 建議 |
| sales_amount | 銷售額主指標 | 必要 |
| sales_target | 達標對照基準 | 必要 |
| achievement_pct | 達標率（如已提供可直接核對） | 建議 |
| units_sold | 補充量化效率（件數） | 必要 |
| asp (avg selling price) | 客單價/產品組合判讀（可由 sales/units 算出） | 建議 |
| sales_ranking | 銷售排名（如已有） | 建議 |
| incentive_game_score | 活動分數主指標 | 必要 |
| game_result | 活動結果（Win/Lose/Level） | 必要 |
| game_ranking | 活動排名（如已有） | 建議 |
| prize_qualification | 是否達獎資格（Y/N/Level） | 必要 |
| attendance_days | 出勤天數（校正公平性） | 建議 |
| working_hours | 工時（校正生產力） | 建議 |
| stock_issue_flag | 缺貨/斷貨標記（解釋低銷售） | 建議 |
| remarks | 特殊註記（新人、調店、請假、活動支援） | 建議 |

### 建議貼上格式（可直接複製）
以 **Tab 分隔** 或「`|`」分隔均可；每列一位 promoter 於單一 campaign period 的結果。

```
campaign_period\tpromoter_name\tstore\tsales_amount\tsales_target\tachievement_pct\tunits_sold\tincentive_game_score\tgame_result\tprize_qualification\tremarks
2026-05-01~2026-05-31\t<NAME>\tStore A\t120000\t100000\t120%\t320\t88\tGold\tY\t-
```

---

## 2) 完整分析框架（正式版使用）

### A. Overall Sales Performance Review（整體銷售表現）
- 總銷售額、總目標、整體達標率。
- 與上期比較（如有上期）：MoM 變化（%）。
- 門店/區域層級：貢獻佔比、達標率差異。

### B. Promoter Performance Ranking（Promoter 銷售排名）
- 以 sales_amount 及 achievement_pct 雙軸排名。
- 補充效率：units_sold、ASP、每工時銷售（如有工時）。
- Top 10 / Bottom 10 清單。

### C. Incentive Game Ranking（活動排名）
- 以 incentive_game_score 排名。
- 分層：Gold/Silver/Bronze 或 Win/Lose。
- 獎勵資格覆蓋率（Qualified / Total）。

### D. Sales Result vs Game Result 對比
- 交叉矩陣（高銷售×高遊戲分、 高銷售×低遊戲分、低銷售×高遊戲分、低銷售×低遊戲分）。
- 一致性指標：銷售排名與遊戲排名相關性（Spearman）。
- 落差名單：銷售前段但遊戲後段、或反向。

### E. Top / Middle / Low Performers 分類
- 建議分組：
  - Top：Achievement ≥110% 或銷售排名前 20%
  - Middle：Achievement 85%~109%
  - Low：Achievement <85%
- 每組輸出：人數、銷售貢獻、平均 game score、獎勵資格率。

### F. 異常表現或落差檢查
- 異常高分低銷售：可能過度偏向遊戲任務。
- 高銷售低分：機制理解不足或非目標行為未被激勵。
- 異常值檢查：極端銷售、缺失值、重複紀錄、目標為 0。

### G. 重點亮點（Highlights）
- 最佳進步、最穩定達標、跨店支援成效。
- 高難度門店仍達標案例。

### H. 主要問題（Issues）
- 低達標門店集中、某區 game engagement 偏低。
- 獎勵門檻造成中段人員動機斷層。

### I. Actionable Follow-up Suggestions
- 1 週內：對 Low segment 做店長+promoter 1:1 correction。
- 下期前：優化遊戲規則權重，使其更貼近銷售 KPI。
- 持續：建立 weekly tracker 與早期預警（<70% target）。

---

## 3) Demo 匯報版本（SAMPLE DATA ONLY / NOT FINAL RESULT）

## **SAMPLE DATA ONLY / NOT FINAL RESULT**

### Executive Summary
- 本期（示範）整體達標率 **96%**，接近目標但未完全達標。
- 銷售排名與遊戲排名呈 **中度正相關**（示範值：0.46），方向一致但仍有落差群組。
- Top performers 貢獻高，但 Middle segment 轉化不足為主要改善機會。

### Key Findings
1. Top 20% Promoters 貢獻示範總銷售 **44%**。  
2. Incentive Game 合格率示範為 **58%**，中段群組合格率偏低。  
3. 出現「高銷售/低遊戲分」與「低銷售/高遊戲分」雙向落差，顯示規則對 KPI 對齊仍可優化。

### Detailed Comparison（示範）

| 分類 | 人數 | 平均 Achievement % | 平均 Game Score | Prize Qualification Rate |
|---|---:|---:|---:|---:|
| Top | 12 | 123% | 84 | 92% |
| Middle | 28 | 96% | 67 | 54% |
| Low | 10 | 71% | 61 | 20% |

| 對比象限 | 定義（示範） | 人數 | 管理解讀 |
|---|---|---:|---|
| Q1 高銷售×高分 | Achievement≥100% & Score≥75 | 14 | 最佳實踐，可複製 |
| Q2 高銷售×低分 | Achievement≥100% & Score<75 | 9 | 規則理解/參與度需提升 |
| Q3 低銷售×高分 | Achievement<100% & Score≥75 | 7 | 遊戲投入高但銷售轉化不足 |
| Q4 低銷售×低分 | Achievement<100% & Score<75 | 20 | 優先改善池 |

### Highlight Cases（示範）
- Case A（Top）：在高目標店仍達 128%，且遊戲分 90+，可作 coaching 標竿。  
- Case B（Gap）：銷售排名前 5，但遊戲分落於中後段，建議短訓練補齊機制。  
- Case C（Potential）：遊戲分高但銷售偏低，疑似客群轉化技巧可再強化。

### Improvement Opportunities（示範）
- 針對 Middle segment 設「微門檻獎勵」，提高 90%→100% 達標轉化。
- 對 Q3 群組追加「closing/upsell」實戰 coaching。
- 對 Q4 群組用店別 weekly checkpoint（目標、話術、陳列、庫存）。

### Recommended Next Actions（示範）
- D+2：完成 gap 名單與責任分配（Sales Coach / Store Manager）。
- D+7：完成第一輪跟進並回報短期拉升結果。
- Next Campaign：調整 game score 權重，提升與銷售 KPI 對齊。

---

## 4) 你下次貼上真實 Excel 文字結果後，我會如何處理

1. **資料整理與清洗**
   - 欄位對齊、名稱標準化（如 `promoter` → `promoter_name`）。
   - 去除重複紀錄、修正百分比格式、數值型轉換。
   - 建立檢查報告：缺失欄位、異常值、可疑資料點。

2. **統一欄位與衍生指標**
   - 自動計算：achievement_pct、ASP、rank、segment。
   - 若你提供 ranking，我會與重算 ranking 做一致性核對。

3. **執行對比分析**
   - Sales vs Game 交叉矩陣。
   - Top/Middle/Low 分層、門店與區域差異。
   - 落差名單與異常檢查（高銷售低分 / 低銷售高分）。

4. **輸出 Final Review Report**
   - Executive summary（管理層 5 行內重點）。
   - Key findings + Detailed tables。
   - Highlight cases + Actionable next actions（按優先級與時程）。

---

## 5) 目前資料不足提示（正式分析前必需）

目前尚未有真實結果，因此**未能產生任何真實排名、達標率或結論**。正式分析至少需你提供：
- campaign_period、promoter_name、store、sales_amount、sales_target、units_sold、incentive_game_score、game_result、prize_qualification。  
其餘建議欄位可提升解讀深度與行動建議精準度。
