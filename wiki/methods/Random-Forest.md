---
title: "Random Forest"
type: method
tags:
  - ml
  - ensemble-learning
  - classification
  - anomaly-detection
aliases:
  - 隨機森林
  - RF
updated: 2026-11-21
sources:
  - "[[2026-Jagadhabi-ML-SAP-Config-Errors]]"
---

# Random Forest (隨機森林)

## 1. 原理簡介

**Random Forest（隨機森林）** 是由 Leo Breiman 於 2001 年提出的一種經典集成學習（Ensemble Learning）演算法。其核心思想是結合 **Bagging（Bootstrap Aggregating）** 與 **隨機特徵選擇（Random Subspace Method）**，建立由大量去相關（Decorrelated）的決策樹所構成的集成模型。

### 核心機制
1. **自助抽樣 (Bootstrap Sampling)**：每棵樹使用從母資料集中有放回抽樣出的子集進行訓練。
2. **隨機特徵分割 (Feature Randomness)**：在樹節點進行切分時，僅從隨機挑選的 $m$ 個特徵子集（通常為 $\sqrt{p}$）中尋找最佳分割點，降低單一主導特徵造成的樹間高相關性。
3. **投票或平均 (Aggregation)**：分類任務採多數決投票（Majority Voting），回歸任務採平均值（Averaging），有效降低模型的變異數（Variance）並大幅減緩過擬合（Overfitting）。

---

## 2. 在系統異常與配置檢測中的應用

在系統與軟體配置分析中，[[Random-Forest]] 長期被視為強大的基準線（Baseline）或首選模型：

- **優勢**：
  - **非線性交互作用**：能天然捕捉多個離散配置參數組合時產生的非線性效應，優於線性 SVM 或單一決策樹。
  - **抗噪性與魯棒性**：企業日誌與配置表常有缺失值與噪音資料，隨機森林具有高容錯能力。
  - **輸出連續機率評分**：可透過各樹預測結果比例計算類別機率，作為異常程度（Anomaly Score）的量化指標。

- **實證對比 (以 SAP 配置檢測為例)**：
  在 [[2026-Jagadhabi-ML-SAP-Config-Errors]] 的實證中，隨機森林達到 **0.93** 的 Accuracy 與 **0.91** 的 F1-Score，全面超越單一 Decision Tree (0.89) 與 SVM (0.90)。

---

## 3. 局限性與現代替代方案

- **缺乏文本與語意理解**：隨機森林僅能處理經特徵工程數值化後的表格資料，無法直接讀取自然語言說明文件、業務規則手冊或長文本日誌。
- **維度擴展瓶頸**：面對數萬個無固定綱要（Schemaless）的超稀疏文本特徵時，效果不如現代神經網絡與大型語言模型（LLM）。

---

## 4. 相關連結
- [[Ensemble-Learning-for-Anomaly-Detection]] - 集成學習異常檢測體系
- [[Configuration-Error-Detection]] - 配置錯誤檢測
- [[ML-vs-LLM-for-Software-Configuration]] - 機器學習與大型語言模型對比
