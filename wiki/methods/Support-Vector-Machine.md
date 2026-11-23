---
title: "Support Vector Machine"
type: method
tags:
  - ml
  - classification
  - anomaly-detection
aliases:
  - 支持向量機
  - SVM
updated: 2026-11-23
sources:
  - "[[2026-Jagadhabi-ML-SAP-Config-Errors]]"
---

# Support Vector Machine (支持向量機)

## 1. 原理簡介

**Support Vector Machine（SVM，支持向量機）** 是一種經典的監督式機器學習演算法。其核心目標是在特徵空間中尋找一個最優超平面（Optimal Hyperplane），使得不同類別樣本點之間的邊界距離（Margin）最大化。對於非線性問題，SVM 藉由核函數技巧（Kernel Trick，如 RBF 核）將低維特徵映射到高維空間進行線性分割。

---

## 2. 在系統配置與異常檢測中的應用與局限

在 [[2026-Jagadhabi-ML-SAP-Config-Errors]] 的實證評測中：
- **表現**：在 8,000 筆 SAP 參數測試中取得 Accuracy 0.90、Precision 0.88、Recall 0.87。
- **優勢**：在決策邊界清晰、資料維度中等時表現穩定。
- **局限**：當企業 ERP 包含數萬項高基數類別特徵與複雜非線性交互時，計算核矩陣開銷較大，整體表現落後於集成樹模型 [[Random-Forest]] (0.93)。

---

## 3. 相關連結
- [[Random-Forest]] - 隨機森林演算法
- [[Decision-Tree]] - 決策樹演算法
- [[Configuration-Error-Detection]] - 配置錯誤檢測
