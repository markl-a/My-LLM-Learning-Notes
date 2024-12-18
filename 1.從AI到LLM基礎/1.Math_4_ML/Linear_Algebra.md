# Linear_Algebra.md

## 目錄
1. 前言
2. 基本定義與符號
    - 標量 (Scalar)
    - 向量 (Vector)
    - 矩陣 (Matrix)
    - 張量 (Tensor)
    - 符號與轉置運算
3. 基本矩陣運算
    - 矩陣相加、標量與矩陣之間的加乘
    - 矩陣與向量/矩陣的乘法
    - 單位矩陣 (Identity Matrix) 與逆矩陣 (Inverse)
    - 矩陣分解舉例：LU 分解、對角矩陣特性
4. 線性獨立與秩 (Rank)
    - 線性獨立 (Linear Independence)
    - 生成子空間 (Span) 與列空間 (Column Space)
    - 秩 (Rank) 的意義
    - 解線性方程組：可解性與有無限多解的判斷
5. 范數 (Norm) 與距離
    - 向量的 Lp 范數
    - 矩陣的 Frobenius 范數
    - 最大范數 (L∞ Norm)
    - 范數在機器學習中的應用（如正則化概念）
6. 特徵分解 (Eigen-Decomposition)
    - 特徵值 (Eigenvalue) 與特徵向量 (Eigenvector) 定義
    - 實對稱矩陣的特徵分解：A = QΛQ^T
    - 特徵值的性質：正定 (Positive Definite)、半正定、奇異、負定等分類
    - 利用特徵分解理解二次形式 (Quadratic Form)
    - PCA (主成分分析) 與特徵分解的關係簡介
7. 奇異值分解 (Singular Value Decomposition, SVD)
    - SVD 定義：A = U D V^T
    - 左奇異向量 (Left Singular Vector)、右奇異向量 (Right Singular Vector)、奇異值 (Singular Value)
    - SVD 的性質與應用（降維、壓縮、PCA）
    - SVD 與特徵分解的差異
8. 線性代數在深度學習與機器學習中的應用
    - 權重矩陣、特徵空間與模型參數化
    - 方程組求解在參數估計中的應用 (如最小二乘問題)
    - 矩陣分解、低秩近似在模型壓縮與加速上的運用
9. 數值穩定性與計算注意事項
    - 上溢 (Overflow) 與下溢 (Underflow)
    - 病態條件 (Ill-conditioning) 與數值方法的穩健性
    - 使用框架（如 NumPy、PyTorch、TensorFlow）執行矩陣運算的小技巧
10. 延伸閱讀與實務參考
    - 更深入的矩陣分解方式（如 Cholesky、QR、Hessenberg）
    - 高等線性代數主題

---

## 1. 前言

線性代數是現代數學與工程科學的核心工具之一，在深度學習和機器學習中更是無所不在。從最基礎的線性模型 (Linear Model) 到深度神經網路的權重矩陣 (Weight Matrix)，再到高階技巧如主成分分析 (PCA)、奇異值分解 (SVD) 與各種優化過程，都需要對線性代數有紮實的理解。

本章節將回顧線性代數的重要概念，涵蓋了向量、矩陣運算、特徵值特徵向量、奇異值分解 (SVD) 等主題，並在結尾連結到機器學習、深度學習實務中最常見的應用場景。

## 2. 基本定義與符號

- **標量 (Scalar)**：一個單獨的數字，如實數 R 中的元素。標量常以斜體小寫字母表示，例如 s。
- **向量 (Vector)**：一列有序數值的集合，如 x ∈ R^n。可將向量視為 n 維空間中的一個點或坐標。通常使用粗體小寫字母 (e.g. **x**)。
- **矩陣 (Matrix)**：一個二維陣列，含有 m × n 個元素。以粗體大寫字母 (e.g. **A**) 表示。A ∈ R^(m×n)。
- **張量 (Tensor)**：更高維度的泛化陣列（超過 2 維），如三維以上結構在深度學習的輸入圖像資料中常出現。
- **轉置 (Transpose)**：矩陣 A 的轉置 A^T 將行、列互換。

## 3. 基本矩陣運算

- **加法與標量乘法**：兩矩陣同形狀下可逐元素相加；標量乘法對每元素同時放大或縮小。
- **矩陣乘法**：若 A 為 m×n，B 為 n×p，則 C = A B 為 m×p 矩陣。C 的元素 C_(i,j) = Σ_k A_(i,k)*B_(k,j)。
- **單位矩陣 (Identity Matrix)**：記為 I，滿足 I x = x，常作為「不改變向量」的單位元素。I 是方陣且對角線為 1，其餘元素為 0。
- **逆矩陣 (Inverse Matrix)**：A 為可逆方陣，A^(-1) 滿足 A A^(-1) = I。若 A 不可逆，則可能需用偽逆 (Pseudo-Inverse)。
  
## 4. 線性獨立與秩 (Rank)

- **線性獨立**：一組向量中無法用其他向量的線性組合來表示該組內的某一成員時，即為線性獨立。
- **秩 (Rank)**：矩陣中最大線性獨立行或列向量的數目，rank(A) 表示 A 的維度「資訊量」或「非退化性」。
- 透過秩與線性獨立性，我們可判定 Ax=b 是否有唯一解、無解或無限多解。

## 5. 范數 (Norm) 與距離

- **向量范數**：如 L2 范數 ∥x∥2 = sqrt(Σ x_i^2)。L1、L∞、以及 Frobeinus 范數 (應用於矩陣) 在深度學習中也很常見。
- 范數用於衡量「大小」或「長度」，在優化、正則化 (Regularization) 與誤差衡量時相當重要。

## 6. 特徵分解 (Eigen-Decomposition)

- **特徵值與特徵向量**：給定方陣 A，若存在非零向量 v 與標量 λ，使得 A v = λ v，則 λ 為 A 的特徵值，v 為對應特徵向量。
- **特徵分解**：若 A 有 n 個線性獨立特徵向量，則 A = V Λ V^(-1)，其中 V 是由特徵向量組成的矩陣，Λ 是特徵值對角矩陣。
- 對實對稱矩陣，可得 A = Q Λ Q^T，其中 Q 為正交矩陣。此在機器學習中很常用，例如 PCA 中以特徵分解找出資料主軸方向。

## 7. 奇異值分解 (Singular Value Decomposition, SVD)

- **定義**：對任意 m×n 的實矩陣 A，可分解成 A = U D V^T，其中 U、V 為正交矩陣，D 為對角矩陣（奇異值在對角線上）。
- **奇異值 (Singular Value)**：D 的對角元素皆為非負實數，代表 A 沿各奇異向量方向的伸展尺度。
- SVD 是 PCA 的理論基礎，也是許多降維 (Dimensionality Reduction) 技術的關鍵，同時可用於矩陣近似、壓縮與正則化。

## 8. 線性代數在機器學習與深度學習中的應用

- 模型參數矩陣 W 在前饋運算 y = W x 中扮演關鍵角色。
- 解線性方程組 Ax = b 是最小二乘 (Least Squares) 問題的基礎，可推廣至迴歸模型參數估計。
- 特徵值、SVD 分解在資料降維、特徵提取 (Feature Extraction)、正則化與神經網路的權重初始化分析中扮演要角。

## 9. 數值穩定性與計算注意事項

- **上溢 (Overflow) 與下溢 (Underflow)**：計算 exp(x) 等函數時，若 x 太大或太小，數值易發生不穩定。
- **病態條件 (Ill-conditioned)**：矩陣條件數大時，微小的輸入誤差將被放大。需採用數值方法如 SVD、QR 分解穩定求解。
- 實務上多使用數值線代函式庫 (NumPy、TensorFlow、PyTorch) 提供高效穩定的矩陣計算。

## 10. 延伸閱讀與實務參考

- 深入了解更多分解法：LU、QR、Cholesky、Jordan Normal Form 等。
- 高等線代主題：非齊次系統、廣義逆、張量分解 (Tensor Decomposition)。
- 推薦閱讀: 《Linear Algebra and Its Applications》、深度學習教科書中關於線代的章節，以及《Matrix Cookbook》作為公式速查表。

