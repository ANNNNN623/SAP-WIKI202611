# LLM Wiki Agent 規範手冊 (AGENTS.md)

本文件是專為 **LLM 研究型個人知識庫（LLM Wiki）** 設計的 Agent 行為指南。本知識庫基於 Andrej Karpathy 提出的 **LLM Wiki 典範**——以「**Obsidian 為 IDE，Agent 為維護工程師，Wiki 為累積與複利的程式碼庫**」，將零散文獻持續編譯為高關聯性、可追溯的結構化網絡。

---

## 核心哲學與三大鐵律

1. **不可侵犯的原始資料層 (`raw/`)**：`raw/` 存放使用者提供的 PDF 原始論文與文獻。**Agent 僅能讀取，絕不可修改或刪除其中的任何檔案。**
2. **複利性與跨文獻整合 (Compounding Knowledge)**：讀取一篇新文獻不是只寫一篇摘要，而是進行「**扇出更新（Fan-out Update）**」——將洞察、實驗數據、衝突矛盾與新技術分發並更新至既有的概念、模型與方法頁面中。
3. **語音與命名慣例 (Language & Terminology)**：
   - **內文主體**：採用繁體中文（台灣習慣用語，如「推論」、「微調」、「嵌入」）。
   - **專有名詞與技術術語**：**務必保留英文原名**（例如：*KV Cache, Speculative Decoding, Self-Attention, Direct Preference Optimization (DPO), Group Relative Policy Optimization (GRPO), FlashAttention, Hallucination, In-context Learning, Mixture of Experts (MoE)*）。
   - **雙向鏈接**：全面使用 Obsidian 相容的雙向鏈接 `[[Page-Name]]` 或 `[[Page-Name|顯示名稱]]`。

---

## 目錄架構與職責分工

```text
LLM Wiki/
├── AGENTS.md                  # 本規範手冊
├── index.md                   # 知識庫全景索引（分類目錄與一句話精煉說明）
├── log.md                     # 操作日誌（紀錄 Ingest / Query / Lint 歷程）
├── raw/                       # [唯讀] 存放 ArXiv PDF 論文或文檔
└── wiki/                      # [Agent 擁有] 自動生成與持續維護之 Markdown 檔案
    ├── sources/               # 論文筆記：每篇論文的萃取記錄 (格式: YYYY-Author-ShortTitle.md)
    ├── concepts/              # 理論與概念：核心原理解析 (如 Self-Attention, RLHF)
    ├── models/                # 模型家族與開源權重：具體架構規格 (如 DeepSeek-R1, Llama-3)
    ├── methods/               # 具體演算法與工程優化：(如 FlashAttention-3, DPO)
    ├── benchmarks/            # 評測指標與數據集：(如 SWE-bench, GSM8K, MMLU-Pro)
    └── synthesis/             # 跨論文主題縱深綜述與技術對比 (如 Reasoning-Paradigms)
```

---

## 頁面 Frontmatter 標準規範

每個在 `wiki/` 下建立的頁面均需包含標準 YAML Frontmatter：

```yaml
---
title: Page Title
type: concept | model | method | benchmark | source | synthesis
tags:
  - llm
  - [領域標籤，如: post-training, inference, attention, reasoning]
aliases:
  - [中文別名或簡稱，如: GRPO, 群組相對策略優化]
updated: YYYY-MM-DD
sources:
  - "[[YYYY-Author-ShortTitle]]"
---
```

---

## 三大核心工作流 (Workflows)

### 1. Ingest 工作流（論文吸收與知識編譯）
當使用者要求解析 `raw/` 內的 PDF 或指定論文時，依照以下步驟執行：

1. **解析讀取文獻**：
   - 完整讀取 `raw/` 下的 PDF 檔案，提取核心論點、數學公式、實驗數據與限制。
2. **生成論文來源筆記 (`wiki/sources/YYYY-Author-ShortTitle.md`)**：
   - 包含：Metadata（標題、作者、單位、ArXiv ID、發布日期）、核心貢獻（Core Contributions）、方法論架構（Methodology）、重要實證數據（Key Empirical Results）、批判性思考（Strengths & Limitations）、相關概念鏈接。
3. **扇出更新（Fan-out Update 5~10 個相關頁面）**：
   - 辨識本論文涉及之 **Concepts / Models / Methods / Benchmarks**。
   - 若頁面已存在：補充最新實驗發現、補充對舊研究的驗證或質疑、更新比較表格。
   - 若頁面不存在：建立該實體頁面，並雙向鏈結至本來源筆記。
   - **特別注意：矛盾與典範轉移**（如某研究推翻過去假設，需在對應概念頁以 `> [!WARNING]` 或專屬章節明確記錄爭鳴）。
4. **維護全景目錄 (`index.md`)**：
   - 在合適的分類下加入新頁面及其一句話總結。
5. **紀錄歷史日誌 (`log.md`)**：
   - 在 `log.md` 最上方或最下方追加記錄：
     ```markdown
     ## [YYYY-MM-DD] ingest | Paper Title
     - **Source**: [[YYYY-Author-ShortTitle]]
     - **Updated Pages**: [[Concept-A]], [[Method-B]], [[Model-C]]
     - **Summary**: 簡要一句話說明本論文的核心價值。
     ```

---

### 2. Query 工作流（綜合檢索與洞察沉澱）
當使用者針對知識庫提問（例如：「目前主流的 Reasoning RL 方法與傳統 PPO 有何差異？」）：

1. **查閱檢索**：先閱讀 `index.md`，並精確檢索相關的 `wiki/` 頁面。
2. **多文獻綜述回答**：基於知識庫累積的內容回答，並標註具體引用頁面（如 `[[DeepSeek-R1]]`、`[[GRPO]]`）。
3. **知識沉澱（Value Retention）**：
   - 若問題與回答具有長期的研究參考價值（如橫向技術對比、演進脈絡盤點），主動建議或直接建立至 `wiki/synthesis/<Topic-Name>.md`，使探索過程再次轉化為知識資產。
4. **記錄至 `log.md`**：簡要紀錄此次重要 Query。

---

### 3. Lint 工作流（知識庫體檢與健康檢查）
定期或依使用者指令執行知識庫健檢：

1. **斷鏈與孤島檢查**：找出未建立但被引用的 `[[Broken-Links]]`，以及沒有任何入鏈的孤立頁面（Orphan Pages）。
2. **觀點衝突與陳舊數據檢視**：確認是否有過時的 SOTA 數據已被新論文推翻但未更新。
3. **研究盲區發掘**：主動提示目前架構中缺失的關鍵拼圖（例如：「已收錄 GRPO 與 DPO，但缺少 PRM（Process Reward Model）專頁」），並建議接下來應補充閱讀的 ArXiv 論文方向。
4. **記錄至 `log.md`**。

---

## 操作注意事項
- **嚴謹客觀**：區分「論文作者聲稱（Claim）」與「實驗驗證（Empirical Proof）」。
- **結構清晰**：善用 GitHub 風格 Callouts（`> [!NOTE]`, `> [!IMPORTANT]`, `> [!WARNING]`）標記技術盲點與研究洞察。
- **維持一致**：嚴格遵循目錄分工，不得隨意在根目錄建立非約定檔案。
