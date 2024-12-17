# My-AI-Learning-Notes
我的AI學習筆記
各章節可包含的筆記方向與程式實作範例
筆記方向：

簡明扼要的概念說明
圖解 (Jay Alammar風格圖解、3D可視化)
常見問題 (FAQ)
實務中碰到的坑與解決策略 (如RLHF的超參數選擇、LoRA rank值設定)
程式實作範例：

Tokenization：使用 Hugging Face tokenizers、sentencepiece 實作並測試中文分詞
微調：用 transformers + peft (LoRA) 實現小規模資料集下的微調
RLHF：模擬一個小型偏好資料集，使用 PPO 對一個小型模型進行簡單演示
評估：實作PPL(Perplexity) 計算，對微調前後的模型結果比較
壓縮：嘗試對一個模型進行4bit QLoRA、GPTQ量化，記錄記憶體使用量及推論速度的變化
部署：在 Colab 或本機環境使用 llama.cpp 部署量化後的模型，測試回答延遲與品質