# My-AI-Learning-Notes
<<<<<<< HEAD

## LLM 部署與運行基礎

### 1.1 LLM 部署模式概述：API、雲端、在地 (Local)  
### 1.2 開源模型 vs. 專有模型 (OpenAI, Anthropic vs. Llama2, GPT-NeoX 等)  
### 1.3 實用工具與框架介紹：LM Studio、Ollama、llama.cpp、Hugging Face Spaces  
### 1.4 實作示例：
- (程式碼) 使用 Hugging Face Transformers 在本地載入並推論簡單模型  
- (程式碼) 使用 OpenAI API 呼叫 GPT-4 生成文字

## LLM 作為 API 與應用程式整合

### 2.1 建立 API 接口：OpenAI API、Hugging Face Inference Endpoints  
### 2.2 與前端整合：Streamlit、Gradio、WebUI  
### 2.3 與自動化工具整合 (例如 UIpath、Zapier)：  
- 概念與流程範例 (將生成的程式碼自動貼回 IDE、或透過 RPA 工具執行特定任務)
### 2.4 實作示例：
- (程式碼) 使用 Flask + OpenAI API 建立簡易的 LLM RESTful API  
- (程式碼) 在 Streamlit 架設 ChatGPT 互動式介面

## Agent 與工具使用

### 3.1 Agent 的概念：ReAct、Toolformer、LangChain Agents  
### 3.2 常用代理(Agents)與工具整合 (Python REPL、搜尋引擎、資料庫查詢)  
### 3.3 LangChain Functions/Tools 使用範例 (調用外部 API)  
### 3.4 實作示例：
- (程式碼) 建立一個 LangChain Agent，能接收使用者指令並自動選擇適合的工具 (如Google Search API 或 Python 執行器)  
- (程式碼) 使用 LangChain + SQL 資料庫工具：自動將使用者問題轉為 SQL 查詢並回傳結果

## 檢索增強生成 (RAG) 基礎

### 4.1 RAG 流程與原理：向量資料庫、Embeddings、檢索器 (Retriever)  
### 4.2 文檔載入器與文件拆分 (PDF、JSON、HTML)  
### 4.3 向量資料庫 (Chroma、Pinecone、Milvus) 基礎與設置  
### 4.4 實作示例：
- (程式碼) 使用 Hugging Face Sentence Transformers 產生向量嵌入  
- (程式碼) 將文檔載入、拆分並存入向量資料庫 (Chroma)  
- (程式碼) 實作簡單的 RAG：使用使用者查詢檢索並附加上下文給 LLM

## 進階 RAG 與多元資料檢索

### 5.1 Query Rewriting、HyDE、多查詢檢索器  
### 5.2 與結構化數據整合 (SQL, Graph DB)  
### 5.3 多工具協作：LLM + RAG + Agents  
### 5.4 實作示例：
- (程式碼) 使用 LangChain 將 RAG 與 SQL 查詢合併，在回應中整合結構化資料  
- (程式碼) 建立複合管道：先使用 RAG 檢索文本，再用 Agent 從 API 取得最新資料補充回答

## 推論優化 (Inference Optimization)

### 6.1 加速推論的技術：量化、Flash Attention、KV Cache、Speculative Decoding  
### 6.2 工具與框架：vLLM、Text Generation Inference (TGI)、CTranslate2  
### 6.3 實作示例：
- (程式碼) 使用 ExLlama 或 QLoRA 量化模型並比較記憶體消耗與推論速度  
- (程式碼) 測試KV Cache對回應時間的影響

## LLM 應用部署

### 7.1 原型開發：Gradio、Hugging Face Spaces 快速上線展示  
### 7.2 生產部署：Serverless(Lambda) vs. 自建GPU叢集(AWS, GCP, Azure)  
### 7.3 邊緣部署：在手機、瀏覽器與IoT環境中運行 LLM (MLC LLM)  
### 7.4 實作示例：
- (程式碼) 使用 Gradio 部署簡單的互動介面並分享  
- (程式碼) 使用 AWS EC2 + GPU + vLLM 部署一個可擴展的 LLM API

## LLM 安全與防禦

### 8.1 Prompt Injection、越獄與資料洩漏風險  
### 8.2 OWASP LLM Top 10 資安議題  
### 8.3 紅隊測試 (Red Teaming) 與防禦策略  
### 8.4 實作示例：
- (程式碼) 在測試環境中嘗試使用 Prompt Injection 並觀察模型反應  
- (程式碼) 加入基本的提示過濾與規則設定，減少攻擊面

## 綜合案例與工作流程示範

### 9.1 實戰案例：RAG + Agent + 部署的端到端流程  
### 9.2 將 LLM 融入自動化工作流程 (UiPath RPA)  
- (範例) 運行 LLM 分析程式碼後，將結果程式碼自動插入IDE
### 9.3 部署至生產環境並持續監控、調優與版本控制

## 附錄

- 工具列表與學習資源匯總  
- Troubleshooting 記錄：常見錯誤與解決方案  
- 可重複使用的程式碼模板 (API呼叫、RAG流程、Agent工具配置)

=======
LLM 部署與運行基礎

1.1 LLM 部署模式概述：API、雲端、在地 (Local)
1.2 開源模型 vs. 專有模型 (OpenAI, Anthropic vs. Llama2, GPT-NeoX 等)
1.3 實用工具與框架介紹：LM Studio、Ollama、llama.cpp、Hugging Face Spaces
1.4 實作示例：
(程式碼) 使用 Hugging Face Transformers 在本地載入並推論簡單模型
(程式碼) 使用 OpenAI API 呼叫 GPT-4 生成文字
LLM 作為 API 與應用程式整合

2.1 建立 API 接口：OpenAI API、Hugging Face Inference Endpoints
2.2 與前端整合：Streamlit、Gradio、WebUI
2.3 與自動化工具整合 (例如 UIpath、Zapier)：
概念與流程範例 (將生成的程式碼自動貼回 IDE、或透過 RPA 工具執行特定任務)
2.4 實作示例：
(程式碼) 使用 Flask + OpenAI API 建立簡易的 LLM RESTful API
(程式碼) 在 Streamlit 架設 ChatGPT 互動式介面
Agent 與工具使用

3.1 Agent 的概念：ReAct、Toolformer、LangChain Agents
3.2 常用代理(Agents)與工具整合 (Python REPL、搜尋引擎、資料庫查詢)
3.3 LangChain Functions/Tools 使用範例 (調用外部 API)
3.4 實作示例：
(程式碼) 建立一個 LangChain Agent，能接收使用者指令並自動選擇適合的工具 (如Google Search API 或 Python 執行器)
(程式碼) 使用 LangChain + SQL 資料庫工具：自動將使用者問題轉為 SQL 查詢並回傳結果
檢索增強生成 (RAG) 基礎

4.1 RAG 流程與原理：向量資料庫、Embeddings、檢索器 (Retriever)
4.2 文檔載入器與文件拆分 (PDF、JSON、HTML)
4.3 向量資料庫 (Chroma、Pinecone、Milvus) 基礎與設置
4.4 實作示例：
(程式碼) 使用 Hugging Face Sentence Transformers 產生向量嵌入
(程式碼) 將文檔載入、拆分並存入向量資料庫 (Chroma)
(程式碼) 實作簡單的 RAG：使用使用者查詢檢索並附加上下文給 LLM
進階 RAG 與多元資料檢索

5.1 Query Rewriting、HyDE、多查詢檢索器
5.2 與結構化數據整合 (SQL, Graph DB)
5.3 多工具協作：LLM + RAG + Agents
5.4 實作示例：
(程式碼) 使用 LangChain 將 RAG 與 SQL 查詢合併，在回應中整合結構化資料
(程式碼) 建立複合管道：先使用 RAG 檢索文本，再用 Agent 從 API 取得最新資料補充回答
推論優化 (Inference Optimization)

6.1 加速推論的技術：量化、Flash Attention、KV Cache、Speculative Decoding
6.2 工具與框架：vLLM、Text Generation Inference (TGI)、CTranslate2
6.3 實作示例：
(程式碼) 使用 ExLlama 或 QLoRA 量化模型並比較記憶體消耗與推論速度
(程式碼) 測試KV Cache對回應時間的影響
LLM 應用部署

7.1 原型開發：Gradio、Hugging Face Spaces 快速上線展示
7.2 生產部署：Serverless(Lambda) vs. 自建GPU叢集(AWS, GCP, Azure)
7.3 邊緣部署：在手機、瀏覽器與IoT環境中運行 LLM (MLC LLM)
7.4 實作示例：
(程式碼) 使用 Gradio 部署簡單的互動介面並分享
(程式碼) 使用 AWS EC2 + GPU + vLLM 部署一個可擴展的 LLM API
LLM 安全與防禦

8.1 Prompt Injection、越獄與資料洩漏風險
8.2 OWASP LLM Top 10 資安議題
8.3 紅隊測試 (Red Teaming) 與防禦策略
8.4 實作示例：
(程式碼) 在測試環境中嘗試使用 Prompt Injection 並觀察模型反應
(程式碼) 加入基本的提示過濾與規則設定，減少攻擊面
綜合案例與工作流程示範

9.1 實戰案例：RAG + Agent + 部署的端到端流程
9.2 將 LLM 融入自動化工作流程 (UiPath RPA)
(範例) 運行 LLM 分析程式碼後，將結果程式碼自動插入IDE
9.3 部署至生產環境並持續監控、調優與版本控制
附錄
工具列表與學習資源匯總
Troubleshooting 記錄：常見錯誤與解決方案
可重複使用的程式碼模板 (API呼叫、RAG流程、Agent工具配置)
透過以上的目錄架構，你可以有條理地複習從 LLM 部署、RAG、Agent、到實際應用整合的各種技術，並在每個章節中加入自己的筆記、重點整理與實務程式範例。
>>>>>>> b146f7e12022537c046f26ef492b379aab28a48a
