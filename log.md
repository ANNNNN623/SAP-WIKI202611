# LLM Wiki 歷史日誌 (Log)

本檔案為 append-only 操作日誌，依照時間倒序（或正序）記錄所有知識庫的生命週期操作（Ingest 論文吸收、Query 關鍵檢索、Lint 體檢維護）。

---

## [2026-11-21] init | 建立 LLM Wiki 知識庫骨架
- **Action**: 初始化知識庫架構與規範
- **Created**:
  - `AGENTS.md` (核心行為準則與 Schema)
  - `index.md` (全景目錄)
  - `log.md` (操作日誌)
  - 目錄骨架：`raw/`, `wiki/sources/`, `wiki/concepts/`, `wiki/models/`, `wiki/methods/`, `wiki/benchmarks/`, `wiki/synthesis/`
- **Next Step**: 使用者可將 PDF 論文放入 `raw/`，開始執行第一次 Ingest。


## [2026-11-21] ingest | Machine Learning Approaches for Detecting Configuration Errors in SAP Systems
- **Source**: [[2026-Jagadhabi-ML-SAP-Config-Errors]]
- **Updated Pages**:
  - [[Configuration-Error-Detection]] (新建概念頁)
  - [[Enterprise-Software-Analytics]] (新建概念頁)
  - [[Random-Forest]] (新建方法頁)
  - [[Ensemble-Learning-for-Anomaly-Detection]] (新建方法頁)
  - [[ML-vs-LLM-for-Software-Configuration]] (新建專題綜述頁)
- **Summary**: 提出了利用隨機森林等集成學習方法檢測企業級 SAP 系統跨模組配置異常的框架，並進一步在 Wiki 中拓展了傳統機器學習與大型語言模型在配置檢測領域的橫向對比。


## [2026-11-23] ingest | 批次吸收三篇企業智慧系統與生成式 AI 論文
- **Sources**:
  - [[2025-Sharma-Intelligent-Systems-SAP]]
  - [[2024-Yadavalli-Hypercare-Signal-Fusion-SAP]]
  - [[2024-Narne-Generative-AI-SAP-Data-Management]]
- **Updated Pages**:
  - [[Enterprise-Software-Analytics]] (補充六大異質訊號層與情緒指標)
  - [[Ensemble-Learning-for-Anomaly-Detection]] (補充異質多分支集成模型架構)
  - [[ML-vs-LLM-for-Software-Configuration]] (更新通用 LLM 在表格數值任務之 20-50% 效能赤字)
- **Created Pages**:
  - [[SAP-Joule]] (新建模型頁：企業級生成式 AI Copilot)
  - [[Tabular-Data-Foundation-Models]] (新建概念頁：表格式原生基礎模型原理與瓶頸破局)
  - [[Multi-Modal-Signal-Fusion-AIOps]] (新建概念頁：多源訊號融合與非結構化情緒指標)
  - [[Time-Series-Anomaly-Detection]] (新建方法頁：LSTM Autoencoder 與 SARIMA 時序預測)
  - [[Autonomous-Enterprise-Systems-Roadmap]] (新建專題綜述頁：邁向自治企業系統演進藍圖)
- **Summary**: 系統性吸收了三篇橫跨 ERP 智慧整合全景、上線期多模態訊號融合（HSF）以及表格式基礎模型的最新論文，將知識庫從古典機器學習檢測成功推進至企業級生成式 AI、多模態 AIOps 與自治閉環。


## [2026-11-23] deep-dive | 深度剖析 Hypercare Signal Fusion (Yadavalli 2024)
- **Source**: [[2024-Yadavalli-Hypercare-Signal-Fusion-SAP]]
- **Updated Pages**:
  - [[2024-Yadavalli-Hypercare-Signal-Fusion-SAP]] (補充 Table 2 特徵映射、Table 3 超參數與 Section VIII AHP 優先級公式)
- **Summary**: 針對 HSF 論文進行細粒度深化解析，補全 Isolation Forest、LSTM Autoencoder、SARIMA、BERT 及 GBDT 的精確超參數設定與層級分析法（AHP）多準則修復佇列數學建模。


## [2026-11-23] presentation | 產出初學者圖解互動式簡報投影片
- **Action**: 將四篇論文的核心技術、數據指標與架構演進轉譯為初學者通俗比喻，製作成獨立的 HTML 投影片。
- **Created**:
  - `wiki/presentations/enterprise_ai_explained.html` (8 頁式互動投影片，支援鍵盤導航、進度條、自適應卡片與比喻圖解)
- **Updated**:
  - `index.md` (新增 Presentations 簡報分類)
- **Summary**: 解決了初學者難以理解純論文數據的痛點，以「四大金剛」協同戰隊的比喻將隨機森林、訊號融合、表格式基礎模型與 Joule Copilot 的演進脈絡立體化呈現。


## [2026-11-23] ingest | Secure-by-Design AI 金融風控與即時串流 (Gopinathan 2024)
- **Source**: [[2024-Gopinathan-Secure-AI-Financial-Risk-SAP]]
- **Created Pages**:
  - [[Secure-by-Design-AI]] (新建概念頁：零信任與原生安全 AI 管線)
  - [[Real-Time-Financial-Risk-Intelligence]] (新建概念頁：即時金融風控與亞秒級預測)
- **Updated Pages**:
  - [[Autonomous-Enterprise-Systems-Roadmap]] (補強自治企業之金融安全生命線防護矩陣)
  - `index.md` (登錄新 Source 與 Concepts)
- **Summary**: 吸收了關於雲端數位銀行在 SAP S/4HANA 環境下實現即時金融風控之架構研究，實證了端到端延遲低於 500ms、結合 Kafka/Spark 串流與 BiLSTM 的零信任預測模型。


## [2026-11-23] submission | 產出完整作業繳交套件與反思報告
- **Action**: 針對作業規範全面核對清單，自動實施全庫雙向 Lint 檢測，修復 2 處斷鏈，並生成完整繳交套件。
- **Created**:
  - `REQUIREMENTS.md` (需求摘要：動機、6 大討論維度與 5 篇論文概覽)
  - `WORKFLOW.md` (Workflow 流程圖：三大工作流閉環與業務資料流)
  - `LINT_REPORT.md` (一次實際執行的檢查報告：全庫 19 頁無斷鏈無孤島)
  - `REFLECTION.md` (反思報告：深入剖析出錯節點與 Shift-Left 檢查前移策略)
  - `SUBMISSION.md` (作業成果繳交總報告)
- **Updated**:
  - `index.md` (收錄繳交檔案專區)
- **Summary**: 作業要求之三大區塊（建 Wiki、繳交項目、反思題目）已達成 100% 完整覆蓋與嚴謹閉環。
