# Optimization_Basics.md

## 目錄
1. 前言
2. 最優化問題的基本概念
    - 目標函數 (Objective Function)、損失函數 (Loss Function)
    - 全域極小值 (Global Minimum) 與局部極小值 (Local Minimum)
    - 鞍點 (Saddle Point) 與平坦區域
    - 凸問題 (Convex Problem) 與非凸問題 (Non-Convex Problem)
3. 基於梯度的一階優化方法
    - 導數、偏導數與梯度 (Gradient)
    - 梯度下降法 (Gradient Descent)
    - 學習率 (Learning Rate) 選擇與調整策略
    - 動量 (Momentum) 與慣性概念
4. 數值計算考量與技巧
    - 浮點數表示與有限精度問題
    - 上溢 (Overflow) 與下溢 (Underflow) 與對數域計算 (Log-space Computation)
    - 病態條件 (Ill-conditioning) 與條件數 (Condition Number) 的影響
    - 數值穩定 (Numerical Stability) 的方法：如使用 `log-sum-exp` 技巧、對輸入正規化
    - 避免在優化過程中因數值誤差導致梯度爆炸 (Exploding Gradient) 或梯度消失 (Vanishing Gradient)
5. 加速收斂的策略與變形
    - 動量 (Momentum) 方法：Nesterov Accelerated Gradient (NAG)
    - 自適應學習率方法：Adagrad、RMSProp、Adam
    - 隨機梯度下降 (Stochastic Gradient Descent, SGD) 與 Mini-batch SGD
    - 隨機性 (Stochasticity) 在優化中的角色
6. 二階與高階方法
    - Hessian 矩陣 (Hessian Matrix) 與二階微分
    - 牛頓法 (Newton’s Method) 與擬牛頓法 (Quasi-Newton Methods)
    - 二階方法的數值問題與計算成本
7. 約束優化 (Constrained Optimization) 基礎
    - 以 Lagrange 乘子法 (Lagrange Multipliers) 處理約束
    - KKT 條件 (Karush–Kuhn–Tucker Conditions) 的概念
    - 實務中常用的簡單投影法 (Projection) 處理參數約束
8. 實務中優化策略的選擇與調適
    - 超參數 (Hyperparameter) 調整：學習率衰減策略 (Learning Rate Decay)、預熱 (Warmup)
    - 混合精度訓練 (Mixed Precision Training) 以改善數值穩定與加速運算
    - Early Stopping、正則化 (Regularization) 與模型優化的平衡
9. 實務案例與建議
    - 深度學習中常見使用 SGD with Momentum 或 Adam
    - 大規模資料集與分佈式訓練下的優化考量
    - 將數值穩定技巧融入損失函數與模型架構設計
10. 延伸閱讀與參考資源

---

## 1. 前言

優化 (Optimization) 是機器學習與深度學習中不可或缺的核心步驟。我們在訓練模型時，需透過對參數空間進行搜索，找到使損失函數 (例如交叉熵、均方誤差) 值最小的參數組合。深度學習中的優化問題通常極為複雜、非凸且含有許多局部極小點、鞍點以及高維度的平坦區域。

本章將介紹優化的基本概念與常用的一階法，重點在梯度下降及其變形（如動量法、自適應學習率法則等）。同時，本章也加入在數值計算上的考量，包括如何處理浮點誤差、上溢下溢問題，並簡述二階方法及約束優化的概念，最後提供實務選擇策略和學習資源。

## 2. 最優化問題的基本概念

- **目標函數 / 損失函數**：優化的目標為最小化或最大化一函數 f(x)。在機器學習中通常最小化訓練損失。

- **全域極小值 (Global Minimum)**：f(x*) ≤ f(x) 對任意 x 成立，x* 為全域最小點。但對複雜非凸問題，找到全域最小往往很難。

- **局部極小值 (Local Minimum)**：f(x*) ≤ f(x) 在 x 鄰近區域成立。在非凸問題中，我們常只能期望找到局部極小點或夠低的代價函數值即可。

- **鞍點 (Saddle Point)**：一點處梯度為 0，但該點同時在某些方向上彎曲向上、在某些方向上彎曲向下，不是極小或極大。在高維空間中，鞍點與平坦區域比局部極小點更加普遍。

- **凸問題 (Convex Problem)**：若目標函數為凸函數，任何局部極小點即為全域極小點。可惜深度學習中多為非凸問題。

## 3. 基於梯度的一階優化方法

- **梯度 (Gradient)**：目標函數對參數向量的偏導數組成的向量，指出上升最快方向。向相反方向走即下降最快。

- **梯度下降法 (Gradient Descent)**：反覆更新 x ← x − ϵ∇f(x)，其中 ϵ 為學習率。若 ϵ 適中且梯度方向可靠，能使 f(x) 遞減。

- **學習率 (Learning Rate)**：控制每步更新幅度。過大可能震盪或發散，過小則收斂慢。實務中可使用動態調整策略，如 Learning Rate Decay 或 Learning Rate Scheduler。

- **動量 (Momentum)**：引入速度概念。將前次梯度更新累積為動量項，可減少優化路徑中不必要的小震動，使收斂更平滑和快速。

## 4. 數值計算考量與技巧

在優化時需處理與數值相關的問題：

- **浮點數近似與有限精度**：電腦中實數以有限位元表示，逼近真實值，導致捨入誤差。

- **上溢 (Overflow) 與下溢 (Underflow)**：計算 exp(x) 等函數時，x 過大或過小會使結果逼近∞或0並喪失精度。  
  解決方法：  
  - 使用對數域計算 (log-space) 來避免下溢。  
  - 在 softmax 計算中先減去最大值，以確保數值穩定。

- **病態條件 (Ill-conditioning)**：若 Hessian 矩陣或問題本身條件數很大，則小幅參數改變也導致目標值巨大變化，需更保守的更新或使用更有彈性的優化器。

- **數值穩定性 (Numerical Stability)**：  
  - 使用 log-sum-exp 計算來避免概率歸一化時的下溢。  
  - 使用適度正則化、梯度裁剪 (Gradient Clipping) 來避免梯度爆炸。  
  - 適度初始化參數和正規化 (Normalization) 輔助收斂。

## 5. 加速收斂的策略與變形

- **Momentum**：透過動量項 (velocity) 將更新方向平滑化，如 v ← βv + (1−β)∇f(x)，x ← x−ϵv。

- **Nesterov Accelerated Gradient (NAG)**：先暫移動一步再計算梯度，能更精準預測下一步動向。

- **自適應學習率方法 (Adaptive Methods)**：  
  - Adagrad：對經常更新的參數給予較小的學習率；對很少更新的參數給予較大學習率。  
  - RMSProp：對梯度平方移動平均以調整學習率。  
  - Adam：同時考慮動量 (一階矩) 與梯度平方 (二階矩) 的估計，自適應校正更新步伐。

- **隨機梯度下降 (SGD)**：每次利用小批次 (mini-batch) 樣本估計梯度，可在高維大數據環境中更快速地進行參數更新。

## 6. 二階與高階方法

- **Hessian 矩陣**：包含二階偏導數，提供函數曲率資訊。

- **牛頓法 (Newton’s Method)**：利用 Hessian 逆矩陣找到臨界點，理想情況下一步即可到達局部極小。但實務上 Hessian 計算昂貴、對數值精度要求高。對非凸問題易陷於鞍點或不合適的臨界點。

- **擬牛頓法 (Quasi-Newton)**：如 L-BFGS，以較低代價近似 Hessian，但在深度學習大規模問題中仍不常使用。

## 7. 約束優化 (Constrained Optimization) 基礎

- 若有參數約束（例如參數必須非負或範數限制），可採  
  - Lagrange 乘子法導出 KKT 條件  
  - 投影法 (Projection) 將更新後的解投回可行域  
  - 在深度學習中較少明示使用 KKT，但某些正則化或特殊層結構等價於對參數的隱性約束。

## 8. 實務中優化策略的選擇與調適

- 選擇優化方法時，SGD with Momentum 或 Adam 是常見首選。  
- 對學習率做衰減，如在訓練中期降低學習率，加速前期收斂並在後期微調。
- 使用混合精度 (Mixed Precision) 計算，可加速訓練，並需留意數值穩定性。

- 過度擬合時，可以透過正則化策略（L2、Dropout）同時改善泛化能力與優化平穩度。

## 9. 實務案例與建議

- 絕大多數深度學習任務直接使用 Adam 或 SGD+Momentum 即可獲得不錯結果。
- 面對梯度消失，可在網路設計上引入殘差結構 (Residual Connections) 或適當初始化。
- 面對梯度爆炸，可嘗試梯度裁剪、正則化、或更小的學習率。

## 10. 延伸閱讀與參考資源

- 推薦閱讀：《Deep Learning》(Goodfellow, Bengio, Courville) 中優化章節及數值計算附錄。
- Nocedal & Wright, "Numerical Optimization" 對傳統優化方法的詳細探討。
- 官方框架文件 (TensorFlow, PyTorch) 關於優化器的 API 說明。

