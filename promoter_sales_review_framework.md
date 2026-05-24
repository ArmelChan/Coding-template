# Promoter Sales Review & Incentive Game Framework (EN Primary / 中文輔助)

> **Audience**: CEO / Retail Leadership  
> **Tone**: Professional, concise, management-ready  
> **Important**: Demo section is clearly separated from formal reporting.

---

## A) Compliance Check Against Requested Requirements

| # | Requirement | Status | Notes |
|---|---|---|---|
| 1 | Data field template (field / purpose / required) | ✅ Met | Included in Section B. |
| 2 | Complete analysis framework (sales ranking, game ranking, comparison) | ✅ Met | Included in Section C. |
| 3 | Demo report clearly marked `SAMPLE DATA ONLY` | ✅ Met | Included in Section D with clear labeling. |
| 4 | User can add data via text + image upload | ✅ Met (Web page) | HTML includes text input area and image uploader. |
| 5 | Data cycle is 7 days per week | ✅ Met | Weekly-cycle rule is defined in Section B/C. |
| 6 | Demo and formal result separation; no fabricated real result | ✅ Met | Explicit policy statement in Section E. |

---

## B) Weekly Data Field Template (7-day cycle)

**Cycle rule**: Each reporting cycle = **7 calendar days** (Week Start Date to Week End Date).

| Field Name | Purpose | Required |
|---|---|---|
| week_start_date | Weekly cycle start date (YYYY-MM-DD) | Yes |
| week_end_date | Weekly cycle end date (YYYY-MM-DD) | Yes |
| campaign_period | Campaign window reference | Yes |
| promoter_name | Promoter identity | Yes |
| promoter_id | Unique ID for de-duplication | Recommended |
| store | Store-level analysis | Yes |
| region | Regional roll-up | Recommended |
| sales_amount | Core sales KPI | Yes |
| sales_target | KPI baseline | Yes |
| achievement_pct | Target achievement ratio | Recommended |
| units_sold | Volume productivity | Yes |
| sales_ranking | Sales rank (if already available) | Recommended |
| incentive_game_score | Core game KPI | Yes |
| game_result | Win/Lose/Level | Yes |
| game_ranking | Game rank (if available) | Recommended |
| prize_qualification | Reward eligibility | Yes |
| attendance_days | Fairness adjustment | Recommended |
| working_hours | Productivity normalization | Recommended |
| stock_issue_flag | Stock constraints marker | Recommended |
| remarks | Contextual comments | Recommended |
| raw_text_input | Original pasted text evidence | Recommended |
| image_attachment_ref | Screenshot/photo reference ID or filename | Recommended |

### Copy/Paste Template (for WhatsApp/Email quick sharing)

```text
week_start_date\tweek_end_date\tcampaign_period\tpromoter_name\tstore\tsales_amount\tsales_target\tunits_sold\tincentive_game_score\tgame_result\tprize_qualification\tremarks
2026-05-18\t2026-05-24\t2026-W21\t<NAME>\tStore A\t120000\t100000\t320\t88\tGold\tY\t-
```

---

## C) Full Analysis Framework (CEO-ready)

1. **Overall Weekly Performance**
   - Total sales, total target, weekly achievement %, trend vs previous week.
2. **Promoter Sales Ranking**
   - Rank by sales amount and achievement %.
   - Top/Middle/Low segments (Top 20%, Middle 60%, Low 20%).
3. **Incentive Game Ranking**
   - Rank by game score and game result tier.
   - Reward qualification rate.
4. **Sales vs Game Comparison**
   - 2x2 matrix: High Sales/High Game, High Sales/Low Game, Low Sales/High Game, Low Sales/Low Game.
   - Gap list for coaching and mechanism optimization.
5. **Exception and Gap Checks**
   - Missing values, duplicate rows, outlier values, target=0 rows.
6. **Highlights / Issues / Actions**
   - CEO one-page outputs: key wins, root issues, 7-day action plan.

---

## D) Demo Report (SAMPLE DATA ONLY / NOT FINAL RESULT)

## **SAMPLE DATA ONLY / NOT FINAL RESULT**

### Executive Summary
- Weekly cycle (7 days) achieved **96%** of target in sample simulation.
- Sales rank and game rank show moderate alignment (sample correlation: **0.46**).
- Priority opportunity: improve Middle segment conversion to 100% target attainment.

### Key Findings (Sample)
- Top 20% promoters contributed **44%** of sample weekly sales.
- Reward qualification rate is **58%** in sample data.
- Bidirectional gap exists: high-sales/low-game and low-sales/high-game cohorts.

### Detailed Comparison (Sample)

| Segment | Headcount | Avg Achievement % | Avg Game Score | Reward Qualification |
|---|---:|---:|---:|---:|
| Top | 12 | 123% | 84 | 92% |
| Middle | 28 | 96% | 67 | 54% |
| Low | 10 | 71% | 61 | 20% |

| Matrix Quadrant | Definition | Headcount | Management Interpretation |
|---|---|---:|---|
| Q1 High Sales / High Game | Achv ≥100% & Score ≥75 | 14 | Replicate best practices |
| Q2 High Sales / Low Game | Achv ≥100% & Score <75 | 9 | Improve game participation |
| Q3 Low Sales / High Game | Achv <100% & Score ≥75 | 7 | Convert engagement into sales |
| Q4 Low Sales / Low Game | Achv <100% & Score <75 | 20 | First-priority intervention pool |

---

## E) Governance: Demo vs Formal Result Separation

- **Demo**: May use sample values for layout/logic validation only.
- **Formal report**: Must use user-provided real data only.
- **No fabricated real outcomes** under any condition.

---

## F) Step 2 — User Input Pre-checklist (before analysis starts)

Please confirm the following 5 items first:

1. Analysis objective (sales review / incentive mechanism evaluation / both)
2. Target audience (CEO / senior leadership / store managers)
3. Data source format (Excel paste / CRM export / mixed)
4. Output usage (internal report / performance review / incentive calibration)
5. Language preference (EN / ZH / bilingual)

---

## G) Step 3 — Phase-by-phase Delivery (conversation-based)

### Phase 1: Data Template Output
- Deliver final field template and copy/paste format.
- Wait for user confirmation on field completeness.

### Phase 2: Analysis Framework Setup
- Deliver full analysis logic and KPI flow.
- Confirm segmentation and comparison rules.

### Phase 3: Demo Report Generation
- Deliver `SAMPLE DATA ONLY` report preview.
- Confirm format for WhatsApp / Email / Slides.

