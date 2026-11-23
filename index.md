# LLM Wiki 全景索引 (Index)

本頁面為知識庫的全景索引，記錄所有由文獻編譯而成的實體與綜述頁面。每當執行 Ingest 或新增主題時，Agent 將持續更新此目錄。

---

## 📚 論文來源 (Sources)
> 存放於 `wiki/sources/`，為各篇論文的精煉提煉與批判性筆記。

- [[2026-Jagadhabi-ML-SAP-Config-Errors]] - 提出基於機器學習與隨機森林的 SAP 企業系統配置錯誤偵測與主動預警架構。
- [[2025-Sharma-Intelligent-Systems-SAP]] - 綜述智慧系統與 SAP ERP 的整合全景、三個探索地平線、Joule 生成式 AI 助理及企業落地挑戰。
- [[2024-Yadavalli-Hypercare-Signal-Fusion-SAP]] - 提出 Hypercare Signal Fusion (HSF) 框架，融合基礎設施、SAP 日誌與戰情室人員情緒的多源異質 AIOps 預警體系。
- [[2024-Narne-Generative-AI-SAP-Data-Management]] - 探討生成式 AI 與表格式原生基礎模型在企業數據管理的應用，揭示通用 LLM 在表格數值任務上落後 20-50% 的瓶頸。
- [[2024-Gopinathan-Secure-AI-Financial-Risk-SAP]] - 提出雲端數位銀行之原生安全 (Secure-by-Design) 即時 AI 風控架構，達成端到端低於 500ms 極速詐欺預測與零信任防護。

---

## 🧠 核心概念 (Concepts)
> 存放於 `wiki/concepts/`，涵蓋 LLM 的基本架構、學習機制、機率理論與表現特徵。

- [[Configuration-Error-Detection]] - 系統與軟體配置錯誤檢測的發展脈絡，從靜態規則、統計機器學習到大型語言模型。
- [[Enterprise-Software-Analytics]] - 企業軟體分析與主動式 AIOps 智能維運架構，從單一指標擴展至六大異質訊號層。
- [[Tabular-Data-Foundation-Models]] - 表格式資料基礎模型深度剖析：為何通用 LLM 在純表格任務上出現顯著效能赤字，以及專用表格式模型的架構突破。
- [[Multi-Modal-Signal-Fusion-AIOps]] - AIOps 中的多源異質訊號融合理念，將遙測指標、事件日誌與終端用戶文字情緒作為先導預警指標。
- [[Secure-by-Design-AI]] - 零信任與原生安全設計理念，如何貫徹於高敏金融資料管線與分散式推論服務。
- [[Real-Time-Financial-Risk-Intelligence]] - 即時金融風控與動態交易詐欺預測體系，藉由串流特徵工程將決策時延壓縮至亞秒級。

---

## 🤖 模型與家族 (Models)
> 存放於 `wiki/models/`，記錄代表性開源與閉源模型之架構規格、訓練細節與版本演進。

- [[SAP-Joule]] - SAP 官方推出的全企業級生成式 AI Copilot 助手，貫穿多業務模組的情境感知語意推理架構與安全信任防線。

---

## ⚙️ 方法與工程技術 (Methods)
> 存放於 `wiki/methods/`，包括預訓練技巧、後訓練演算法（RLHF/DPO/GRPO）、推論加速、量化與長文本技術。

- [[Random-Forest]] - 隨機森林集成演算法原理及其在結構化日誌與參數異常檢測中的應用。
- [[Decision-Tree]] - 單一決策樹分類原理與在複雜高維參數檢測下的過擬合局限性。
- [[Support-Vector-Machine]] - 支持向量機最大間隔超平面原理與在 ERP 參數分類中的實證表現。
- [[Ensemble-Learning-for-Anomaly-Detection]] - 結合多個基學習器以降低變異數並捕捉非線性參數約束之集成檢測架構（含同質與異質多分支體系）。
- [[Time-Series-Anomaly-Detection]] - 時間序列異常檢測與預測演算法體系（SARIMA, LSTM Autoencoder, LSTM Forecaster）。

---

## 📊 評測基準 (Benchmarks)
> 存放於 `wiki/benchmarks/`，包含模型評測數據集、排行榜、評判指標與已知局限。

*尚無獨立基準條目（相關數據現暫存於各 Source 筆記中）。*

---

## 🔬 專題綜述與對比 (Synthesis)
> 存放於 `wiki/synthesis/`，跨多篇文獻的橫向技術對比、技術典範轉移脈絡與深度研究報告。

- [[ML-vs-LLM-for-Software-Configuration]] - 橫向對比傳統表格機器學習、通用語言模型與表格式原生基礎模型在軟體配置領域的技術優劣，展望階層式混合管線。
- [[Autonomous-Enterprise-Systems-Roadmap]] - 邁向自治企業系統的演進藍圖：從單點機器學習解決方案、多源 AIOps 訊號融合到基礎模型自治閉環。

---

## 📽️ 簡報與視覺化 (Presentations)
> 存放於 `wiki/presentations/`，將艱深的學術文獻轉化為適合教學、簡報與向非技術人員說明的互動式投影片。

- [enterprise_ai_explained.html](file:///c:/Users/USER/Desktop/LLM%20Wiki/wiki/presentations/enterprise_ai_explained.html) - 《走進企業 AI 與 LLM 的真實世界：從修水管到智慧大腦》10 站全景 Graph 導覽互動投影片。採用韓系簡約燕麥暖色風格，內建頂部可點擊跳轉 Minimap，由「倉鼠助教・薯泥」全程生動伴讀。

---

## 📑 作業繳交與評審檔案 (Submission Deliverables)
> 依照作業要求產出之正式繳交套件：

- [SUBMISSION.md](file:///c:/Users/USER/Desktop/LLM%20Wiki/SUBMISSION.md) - 作業完整成果繳交總報告（含核對清單、架構精華與反思總攬）
- [REQUIREMENTS.md](file:///c:/Users/USER/Desktop/LLM%20Wiki/REQUIREMENTS.md) - 需求摘要（記錄先討論後生成之 6 大維度決策與 5 篇論文概覽）
- [AGENTS.md](file:///c:/Users/USER/Desktop/LLM%20Wiki/AGENTS.md) - Agent 行為規範手冊（定義三大鐵律、Frontmatter 規範與三大工作流）
- [WORKFLOW.md](file:///c:/Users/USER/Desktop/LLM%20Wiki/WORKFLOW.md) - 核心端到端 Workflow 流程圖（含三大作業閉環與 5 篇論文資料流架構圖）
- [LINT_REPORT.md](file:///c:/Users/USER/Desktop/LLM%20Wiki/LINT_REPORT.md) - 一次實際執行的檢查報告（真實掃描全庫 19 頁、2 處斷鏈修復歷程與數據衝突對齊）
- [REFLECTION.md](file:///c:/Users/USER/Desktop/LLM%20Wiki/REFLECTION.md) - 深度工程反思（回答「哪個節點最常出錯？你把檢查往前移到了哪裡？」）
