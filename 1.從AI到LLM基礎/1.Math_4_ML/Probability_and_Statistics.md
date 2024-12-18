# Probability_and_Statistics.md

## 目錄
1. 前言
2. 基本機率概念
    - 隨機變數 (Random Variable)
    - 機率質量函數 (PMF) 與 機率密度函數 (PDF)
    - 邊際分佈與條件分佈
    - 獨立性與條件獨立性
    - 貝葉斯機率觀點
3. 常用分佈介紹
    - Bernoulli 與 Multinoulli 分佈
    - 高斯 (正態) 分佈與多變量高斯
    - Exponential 分佈與 Laplace 分佈
    - Dirac delta 與 經驗分佈 (Empirical Distribution)
    - 混合分佈 (Mixture Distribution) 與高斯混合模型 (GMM)
4. 數值特徵：期望值、變異數、協方差
    - 期望值 (Expectation)
    - 變異數 (Variance) 與標準差 (Standard Deviation)
    - 協方差 (Covariance) 與相關係數 (Correlation)
    - 向量與矩陣的協方差矩陣
5. 機率論與信息論
    - 資訊量 (Information) 與 自信息 (Self-Information)
    - 熵 (Entropy)
    - KL 散度 (Kullback-Leibler Divergence)
    - 交叉熵 (Cross-Entropy) 與機器學習中常用的損失函數
6. 最大似然估計 (Maximum Likelihood Estimation, MLE) 與貝葉斯推論
    - Likelihood 函數定義
    - MLE 的求解思路與範例（如高斯分佈參數估計）
    - Maximum A Posteriori (MAP) 估計
    - 全貝葉斯 (Full Bayesian) 推論概念
    - 先驗 (Prior) 與後驗 (Posterior) 分佈
    - Bayes 定理及其在機器學習中的應用
7. 統計推論與取樣方法
    - 點估計與區間估計
    - 常見的估計量特性：偏差 (Bias)、一致性 (Consistency)、有效性 (Efficiency)
    - 蒙地卡羅 (Monte Carlo) 取樣
    - 馬可夫鏈蒙地卡羅 (MCMC)
    - 近似推論 (Approximate Inference) 與變分推論 (Variational Inference)
8. 在機器學習與深度學習的應用
    - 機率模型在分類、回歸問題中的角色：預測輸出分佈與不確定性衡量
    - 確率性梯度下降 (Stochastic Gradient Descent) 的理論基礎與隨機取樣
    - 使用最大似然原則來推導損失函數（如 cross-entropy 對應於訓練分類模型時最大化觀測資料的 likelihood）
    - 經驗分佈與訓練資料集：從資料估計分佈
    - 正則化 (Regularization) 與先驗分佈的關係
9. 數值計算與機率計算的注意事項
    - 數值穩定性：計算對數機率 (log probability) 以避免下溢 (Underflow)
    - 使用 log-sum-exp 技巧來計算歸一化常數
    - 大數法則 (Law of Large Numbers) 與中心極限定理 (Central Limit Theorem) 在估計平均值、方差時的重要性
10. 延伸閱讀與資源

---

## 1. 前言

在機器學習與深度學習中，我們常面對不確定性。為了表達與處理不確定性，機率論 (Probability Theory) 是最自然的框架。透過機率，我們可以描述資料、模型參數與預測結果的不確定性。

同時，統計學 (Statistics) 提供了從數據中估計模型參數、衡量不確定性並進行推論的工具。無論是簡單的線性回歸模型或是複雜的深度神經網路，機率與統計都是底層的支柱。

本章將回顧機率論與統計的基本概念，介紹常用的分佈模型、資訊理論以及最大似然估計等方法，並深入探討這些概念在機器學習實務中扮演的關鍵角色。

## 2. 基本機率概念

- **隨機變數 (Random Variable)**：用來描述可能結果的數值映射。隨機變數可離散（如擲硬幣）或連續（如測量溫度）。

- **機率質量函數 (PMF)**：對離散型隨機變數 x，P(x) 給出各個可能值的機率。  
  例如，擲硬幣正面向上的機率 p，就可由一個 Bernoulli 分佈描述。

- **機率密度函數 (PDF)**：對連續型隨機變數 x，p(x) 為非負函數，其積分為 1。事件在單點的機率為 0，需透過積分求區間機率。

- **邊際分佈 (Marginal Distribution)**：由聯合分佈 P(x,y) 經由對 y 求和或積分得到 P(x)。  
- **條件分佈 (Conditional Distribution)**：P(y|x) 表示在已知 x 後，y 的分佈情形。

- **獨立性 (Independence)**：若 P(x,y)=P(x)P(y)，x 與 y 稱為獨立。  
- **條件獨立性 (Conditional Independence)**：在已知 z 時，x 與 y 才獨立，記為 x⊥y|z。

- **貝葉斯機率 (Bayesian Probability)**：將機率視為主觀信念的強度，而非僅是事件相對頻率。

## 3. 常用分佈介紹

- **Bernoulli 分佈**：二值型隨機變數（0 或 1），P(x=1)=ϕ。
- **Multinoulli (Categorical) 分佈**：對 k 個類別，每類概率 p_i。
- **高斯 (正態) 分佈**：在 R 上為鐘形曲線，以均值 µ 與變異數 σ² 定義。在高維空間擴展為多變量高斯，由均值向量 µ 與協方差矩陣 Σ 定義。
- **Exponential / Laplace 分佈**：常用於表示有界下限或帶有尖峰的分佈形狀。
- **Dirac delta / 經驗分佈**：用 delta 函數集中概率質量，經驗分佈用於描述訓練數據的觀測。
- **混合分佈 (Mixture Distribution)**：如高斯混合模型 (GMM)，將多個分佈加權合成，用以表達更複雜的資料型態。

## 4. 數值特徵：期望值、變異數、協方差

- **期望值 (Expectation)**：隨機變數 X 的平均值 E[X]。對離散分佈為 sum_x P(x)x，對連續分佈為 ∫ x p(x) dx。

- **變異數 (Variance)**：Var(X)=E[(X−E[X])²]，衡量數值散佈程度。

- **協方差 (Covariance)**：Cov(X,Y)=E[(X−E[X])(Y−E[Y])], 描述 X, Y 線性相關程度。  
  協方差矩陣 (Covariance Matrix) 是衡量多維分佈的尺度與形狀的關鍵。

## 5. 機率論與信息論

- **自信息 (Self-Information)**：不可能事件發生帶來較多信息，常用 I(x)=−log P(x) 定義資訊量。

- **熵 (Entropy)**：H(X)=E[−log P(X)]，衡量隨機變數不確定性程度。

- **KL 散度 (Kullback-Leibler Divergence)**：DKL(P||Q)=E_P[log P(X)−log Q(X)]，衡量分佈 P 與 Q 的差異，不對稱且非負。

- **交叉熵 (Cross-Entropy)**：H(P,Q)=H(P)+DKL(P||Q) = E_P[−log Q(X)]，在機器學習中常用作訓練分類模型的損失函數。

## 6. 最大似然估計 (MLE) 與貝葉斯推論

- **似然函數 (Likelihood)**：給定參數 θ 的模型 p(x|θ)，對觀察資料集 D={x^(i)}，似然為 L(θ)=∏_i p(x^(i)|θ)。最大似然估計尋找使 L(θ) 最大的 θ。

- MLE 不考慮先驗資訊，若加入先驗 p(θ)，則可使用 Bayes 定理得後驗 p(θ|D) ∝ p(D|θ)p(θ)。  
  最大化後驗 (Posterior) 稱為 MAP 估計。

- 在貝葉斯方法中，θ 本身視為隨機變數，使用 p(θ|D) 描述參數不確定性，可進行完整的貝葉斯推論，如求參數後驗平均值。

## 7. 統計推論與取樣方法

- **統計推論**：根據樣本對母體分佈進行推論，包括點估計與區間估計（信賴區間）。

- **估計量性質**：  
  - 有偏 (Bias) 或無偏：估計量的期望值是否等於真值。  
  - 一致性 (Consistent)：樣本數增大，估計量收斂真值。  
  - 有效性 (Efficiency)：在一定條件下誤差最小的估計方法。

- **蒙地卡羅方法 (Monte Carlo)**：利用隨機取樣近似期望值或積分。

- **MCMC (Markov Chain Monte Carlo)**：透過馬可夫鏈產生依分佈收斂的樣本，進行複雜後驗分佈估計。

- **變分推論 (Variational Inference)**：將複雜的後驗分佈近似為較簡單的分佈，透過最小化 KL 散度找近似解。

## 8. 在機器學習與深度學習的應用

- **模型不確定性**：以機率模型對預測結果給出不確定性量化。

- **損失函數連結最大似然**：例如交叉熵作為訓練分類模型的損失函數，可視為最大化資料在模型下的對數似然。

- **SGD (Stochastic Gradient Descent)**：隨機抽樣小批量 (mini-batch) 訓練，透過資料的邊際分佈估計目標函數的梯度。

- **貝葉斯深度學習**：透過先驗與後驗估計，提升模型對新情境的適應，及對不確定性的量化能力。

- **正則化與先驗**：將偏好稀疏參數或平滑解的偏見以先驗形式表達，有助於防止過度擬合。

## 9. 數值計算與機率計算的注意事項

- **數值穩定性**：計算非常小的機率時採用對數空間 (log probabilities) 避免下溢問題。對計算 softmax、歸一化常數時使用 log-sum-exp 技巧。

- **大數法則與中心極限定理**：保證在樣本數充足時，樣本平均接近母體平均，且合適情況下和高斯分佈產生關聯。這些理論支撐了以樣本近似期望的計算方法與漸近分析。

## 10. 延伸閱讀與資源

- 建議閱讀：《Pattern Recognition and Machine Learning》(Bishop) 中的機率分佈與貝葉斯推論章節。
- 《Deep Learning》 (Goodfellow, Bengio, Courville) 對機率論與信息論有清晰的介紹，並在深度學習應用上深入探討。
- 線上資源如 The Matrix Cookbook（對機率與線代部分有助記公式）與統計學入門課程可補充基礎概念。
