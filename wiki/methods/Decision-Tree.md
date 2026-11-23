---
title: "Decision Tree"
type: method
tags:
  - ml
  - classification
  - tree-models
aliases:
  - 決策樹
  - DT
updated: 2026-11-23
sources:
  - "[[2026-Jagadhabi-ML-SAP-Config-Errors]]"
---

# Decision Tree (決策樹)

## 1. 原理簡介

**Decision Tree（決策樹）** 是一種非參數監督式學習演算法，透過遞迴劃分特徵空間構建樹狀決策規則（如 ID3, C4.5, CART）。節點分割準則常基於資訊增益（Information Gain）或基尼不純度（Gini Impurity）。

---

## 2. 在企業配置檢測中的基準角色

在 [[2026-Jagadhabi-ML-SAP-Config-Errors]] 中作為基線（Baseline）模型：
- **表現**：Accuracy 0.89、Precision 0.86、Recall 0.84。
- **優勢**：可解釋性高，規則以 if-then 形式直觀呈現。
- **局限**：單一決策樹極易對訓練集過擬合（Overfitting），在捕捉跨模組複雜交互時泛化能力不足，因而催生了基於 Bagging 的集成演算法 [[Random-Forest]]。

---

## 3. 相關連結
- [[Random-Forest]] - 隨機森林演算法
- [[Support-Vector-Machine]] - 支持向量機
- [[Configuration-Error-Detection]] - 配置錯誤檢測
