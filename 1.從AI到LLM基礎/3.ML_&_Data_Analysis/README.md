## 1_ML_and_Data_Analysis/

### 0_Introduction_and_Environment_Setup
- 說明文件：對本資料夾內容架構的簡介與學習路徑說明
- 環境設定指南（Python、Conda、Notebook 環境、資料庫連接）
- 常用套件介紹（NumPy、Pandas、Matplotlib、Scikit-learn、Spark 等）

### 1_Data_Acquisition_and_Analysis
- **Data_Sources.md**：描述常見資料來源（CSV、SQL 資料庫、NoSQL、API 爬取）
- **Data_Cleaning_and_Processing.ipynb**：缺失值處理、異常值檢測、類別特徵編碼、數值轉換
- **Exploratory_Data_Analysis.ipynb** (EDA)：統計量、相關係數、繪圖（箱型圖、直方圖、散佈圖）、資料分佈、主成分分析 (PCA) 用於初步降維探索
- **Feature_Engineering.ipynb**：特徵選擇、特徵縮放、特徵組合、類別特徵 One-Hot Encoding、Embeddings（若需）

### 2_Traditional_ML_Algorithms
- **Linear_Models.ipynb**：線性回歸、羅吉斯迴歸
- **Tree_Based_Models.ipynb**：決策樹、隨機森林、梯度提升樹 (XGBoost、LightGBM)
- **SVM_and_KNN.ipynb**：支援向量機、k 最近鄰
- **Naive_Bayes.ipynb**：樸素貝葉斯分類器
- **Model_Evaluation_and_Metrics.ipynb**：訓練/驗證/測試集劃分、Cross-Validation、Accuracy、Precision、Recall、F1 Score、AUC、MSE、MAE、R²
- **Model_Selection_and_Parameter_Tuning.ipynb**：GridSearchCV、RandomSearch、Bayesian Optimization

### 3_Kaggle_Case_Studies
- **Kaggle_Competition_1.ipynb**：以某個 Kaggle 常見入門競賽（如泰坦尼克生存預測）為例，從 EDA、Feature Engineering、模型訓練到提交預測結果
- **Kaggle_Competition_2.ipynb**：進階資料集（如房價預測），比較不同模型表現、使用集成方法提升準確率
- **Kaggle_Tips_and_Tricks.md**：整理常用方法、特徵工程想法、加強模型泛化的策略

### 4_Distributed_Computing_and_BigData_Processing
- **Introduction_to_Distributed_Computing.md**：分散式運算的概念與大數據生態系（Hadoop、Spark）
- **Spark_Basics.ipynb**：使用 PySpark 進行資料讀取、轉換、簡單分析
- **Scaling_ML_Models.ipynb**：在分散式環境中訓練 ML 模型（Spark MLlib 範例）
- **ETL_Pipeline_Integration.md**：ETL （Extract, Transform, Load）流程概念、將數據處理管線整合到日常工作中
- **Data_Pipeline_Demo.ipynb**：展示如何在分散式環境中執行從資料擷取、清理到模型訓練的流程

### 5_Best_Practices_and_MLOps_Basics
- **Model_Deployment_Introduction.md**：基本部署模型觀念（非深度學習模型的 Web API 建置）
- **Version_Control_and_Experiment_Tracking.md**：DVC、MLflow、Git 等工具簡介
- **Scalability_and_Performance_Tuning.md**：模型與數據的效能調校方法

