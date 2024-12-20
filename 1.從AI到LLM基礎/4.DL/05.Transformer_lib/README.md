# Hugging Face Libraries for Deep Learning

Hugging Face 提供了多個開源庫，專注於深度學習、自然語言處理（NLP）以及生成式 AI。這份文檔涵蓋了 Hugging Face 的主要庫及其用途，幫助開發者快速了解和使用這些工具。

---

## 1. Transformers

### 簡介
[Transformers](https://github.com/huggingface/transformers) 是一個流行的開源庫，提供主流的預訓練模型，適用於 NLP、圖像處理、多模態等任務。

### 功能
- 支援 PyTorch 和 TensorFlow 框架。
- 提供數百種預訓練模型（如 BERT、GPT、T5）。
- 支援文本分類、生成、翻譯等多種任務。

---

## 2. Datasets

### 簡介
[Datasets](https://github.com/huggingface/datasets) 提供超過 10,000 種數據集，適用於 NLP、計算機視覺、音頻等。

### 功能
- 快速下載、清洗、處理數據。
- 與 Transformers 無縫集成。
- 高效處理大規模數據。

---

## 3. Tokenizers

### 簡介
[Tokenizers](https://github.com/huggingface/tokenizers) 是一個高效的文本預處理工具，專注於 NLP 分詞。

### 功能
- 使用 Rust 開發，速度極快。
- 支援 BPE、WordPiece、SentencePiece 等分詞算法。
- 與 Transformers 完美結合。

---

## 4. Accelerate

### 簡介
[Accelerate](https://github.com/huggingface/accelerate) 簡化了分布式訓練和多設備模型加速。

### 功能
- 支援單 GPU、多 GPU 和 TPU 訓練。
- 簡化深度學習並行化配置。

---

## 5. Diffusers

### 簡介
[Diffusers](https://github.com/huggingface/diffusers) 專注於生成模型（如擴散模型），用於圖像和音頻生成。

### 功能
- 提供預訓練模型和擴散模型工具。
- 適用於藝術創作、圖像修復等任務。

---

## 6. Hugging Face Hub

### 簡介
[Hugging Face Hub](https://huggingface.co) 是一個集中倉庫，提供模型、數據集和應用。

### 功能
- 託管和分享模型、數據集。
- 支援直接從雲端加載。

---

## 7. Evaluate

### 簡介
[Evaluate](https://github.com/huggingface/evaluate) 是一個評估工具庫，用於測試模型的性能。

### 功能
- 提供常見評估指標（如 BLEU、ROUGE）。
- 與 Datasets 無縫整合。

---

## 8. PEFT (Parameter-Efficient Fine-Tuning)

### 簡介
[PEFT](https://github.com/huggingface/peft) 支援參數高效微調，適合資源有限的環境。

### 功能
- 支援 LoRA 等多種高效微調方法。
- 減少計算資源需求。

---

## 9. Hugging Face Optimum

### 簡介
[Optimum](https://github.com/huggingface/optimum) 用於模型的性能優化，支援硬體加速。

### 功能
- 與硬體廠商深度集成。
- 支援 ONNX Runtime、TensorRT。

---

## 如何開始使用？

### 安裝
使用 pip 安裝 Hugging Face 的庫：
```bash
pip install transformers datasets tokenizers accelerate diffusers
```

### 官方文檔
- [Transformers 文檔](https://huggingface.co/docs/transformers/)
- [Datasets 文檔](https://huggingface.co/docs/datasets/)
- [Tokenizers 文檔](https://huggingface.co/docs/tokenizers/)
- [Diffusers 文檔](https://huggingface.co/docs/diffusers/)

---

## 貢獻與社群支持

歡迎對 Hugging Face 的開源項目進行貢獻！
- 官方 GitHub: https://github.com/huggingface
- 社群論壇: https://discuss.huggingface.co

---

了解更多，請訪問 [Hugging Face 官方網站](https://huggingface.co)。
