# DKA／HHS 處置導航

依 **ADA／EASD／JBDS／AACE／DTS 2024 高血糖危象共識**製作的互動工具：輸入檢驗值後自動判斷 DKA、HHS 或兩者合併與嚴重度，依鉀離子決定 insulin 能否開始，計算輸液與 insulin 滴速、何時加 dextrose，追蹤變化速率，並判斷緩解條件與轉換皮下 insulin。

線上版：https://yht5582-source.github.io/DKA-HHS/

> ⚠️ **僅供臨床流程輔助與教學，不取代臨床判斷。** 胰島素、鉀、碳酸氫鈉與輸液請依院內處方與規範。

## 功能

| 區塊 | 內容 |
|---|---|
| 診斷 | DKA 三條件（D 血糖 ≥200 或已知糖尿病、K β-HB ≥3.0 或尿酮 ≥2+、A pH <7.3 或 HCO₃⁻ <18）；嚴重度（輕、中、重）；HHS（血糖 ≥600、有效滲透壓 >300 或總滲透壓 >320、無明顯酮症與酸中毒）；兩者合併；血糖正常型 DKA |
| 輸液 | 前 2–4 小時 500–1,000 mL/h；高齡或心、腎衰竭改用 250 mL 小量；校正鈉 |
| 鉀 | K <3.5 暫停 insulin、KCl 約 10 mmol/h；K 3.5–5.0 每公升加 20–30 mmol；K >5.0 暫不補，2 小時後複查 |
| Insulin | DKA 0.1 U/kg/h、HHS 0.05 U/kg/h、合併依 DKA；自動換算 U/h 與 mL/h；血糖 <250 時減為 0.05 U/kg/h；早期基礎型 insulin 0.15–0.3 U/kg |
| Dextrose | DKA 血糖 <250 mg/dL 加 5–10% dextrose；血糖正常型 DKA 一開始就加；HHS 依院內規範於 250–300 mg/dL 加入 |
| 其他 | pH <7.0 考慮碳酸氫鈉；嚴重低血磷；SGLT2 抑制劑 |
| 追蹤 | 血糖、β-HB（或有效滲透壓）、HCO₃⁻、K 趨勢圖；每筆之間的變化速率，未達或超過目標時標紅並提示 |
| 緩解 | DKA：β-HB <0.6 且（pH ≥7.3 或 HCO₃⁻ ≥18）；HHS：有效滲透壓 <300、血糖 <250、尿量 >0.5 mL/kg/h、意識恢復 |
| 轉換 | 停 IV insulin 前 1–2 小時給基礎型；basal-bolus；每日總量 0.3–0.6 U/kg 或依住院前劑量 |
| 計算 | Anion gap、白蛋白校正 AG、delta ratio、有效與總滲透壓、校正鈉（1.6 與 2.4） |

其他功能：
- **床位列**：顯示 DKA、HHS、低血鉀、已緩解等狀態。
- **示範病例**：空白床位可載入，頁面上會標示「示範病例」。
- **一鍵複製摘要**：可貼到病歷。

## 變化速率目標

- **DKA（JBDS）**：β-HB 每小時下降 ≥0.5 mmol/L、HCO₃⁻ 每小時上升 ≥3 mmol/L、K 維持 4–5。未達標時提示可將 insulin 增加 1 U/h。
- **HHS（2024 共識）**：血糖每小時下降 ≤90–120 mg/dL、有效滲透壓每小時下降 3–8 mOsm/kg、24 小時內 Na 下降 ≤10 mmol/L。

## 使用方式

直接用瀏覽器開啟 `index.html` 即可，不需安裝或建置。

## 在地化設定

| 項目 | 位置 |
|---|---|
| 床號 | 網頁右側「床號設定」 |
| Insulin 濃度 | 網頁「病人資料」（預設 1 U/mL） |
| 診斷與嚴重度 | `<script>` 內 `diagnose()` |
| 處置步驟與切點 | `plan()` |
| 緩解條件 | `resolved()` |
| 變化速率目標 | `flagRates()` |
| 示範病例 | `loadDemo()` |

## 資料與隱私

- 所有資料只存在該瀏覽器的 `localStorage`，不會上傳；不同電腦、不同瀏覽器的資料各自獨立。
- 只記錄床號與檢驗值，請勿輸入姓名或病歷號。

## 依據

1. Umpierrez GE, Davis GM, ElSayed NA, et al. Hyperglycemic crises in adults with diabetes: a consensus report. *Diabetes Care* 2024;47:1257–1275. [doi:10.2337/dci24-0032](https://doi.org/10.2337/dci24-0032)（同步刊登於 *Diabetologia* 2024）
2. Joint British Diabetes Societies for Inpatient Care. The management of diabetic ketoacidosis in adults；The management of the hyperosmolar hyperglycaemic state in adults.
3. Kitabchi AE, et al. Hyperglycemic crises in adult patients with diabetes. *Diabetes Care* 2009;32:1335–1343.
4. Katz MA. *N Engl J Med* 1973;289:843–844；Hillier TA, et al. *Am J Med* 1999;106:399–403.

## 授權

請依使用單位規定自行選擇授權方式（例如 MIT）。
