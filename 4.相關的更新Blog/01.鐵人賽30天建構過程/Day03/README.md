Day03:
1.llm 模型內容:Create a Large Language Model from Scratch with Python – Tutorial 學習紀錄
這個是https://www.youtube.com/watch?v=UU1WVnMk4E8的學習紀錄

1.1 **Intro (0:00:00)**
   - 課程介紹，包括目的和目標。講師強調本課程將帶領學員從頭開始建立大型語言模型，不要求高深的數學背景，適合初學者。
這段文字介紹了課程的目標和設計理念。講師Elia Arleds強調，該課程旨在從零開始教授大型語言模型的構建過程，並特別適合沒有微積分或線性代數基礎的初學者。課程靈感來自Andrej Karpathy的“從頭開始構建GPT”講座，內容涵蓋數據處理、基礎數學以及Transformer模型等，講師會逐步帶領學員理解各個概念。

課程要求學員具備基本的Python知識（約三個月的經驗），但不要求深入的數學背景。重點是學員需要投入時間和精力來學習這些不常見的資料和技術。講師強調，所有計算將在本地進行，不會涉及付費數據集或雲計算。課程設置考慮到不同操作系統（如macOS和Windows）間的兼容性，並使用SSH工具來連接不同設備進行開發。

總之，課程將以循序漸進的方式講授，從基礎開始，逐漸進入更複雜的內容，並使用邏輯類比和逐步示例來幫助學員理解。

1.2. **Install Libraries (0:03:25)**
   - 安裝必需的Python庫，包括`matplotlib`、`numpy`等，這些工具對於數據處理和模型訓練至關重要。
這邊介紹了設置開發環境的具體步驟。首先，講師建議使用Anaconda Prompt來管理機器學習相關的工具，並推薦使用Jupyter Notebook進行項目開發。為了隔離不同項目的依賴關係，建議在目標目錄中創建一個虛擬環境。在這個案例中，虛擬環境被命名為"CUDA"，以便後續可以利用GPU進行加速運算。

講師詳細說明了創建虛擬環境的過程，包括使用Python命令python -m venv CUDA來創建環境，然後啟動這個環境。啟動後，可以開始安裝所需的Python庫，如matplotlib、numpy和py-lzma等，這些工具對數據處理和可視化非常重要。同時，還需要安裝IPY kernel以便在Jupyter Notebook中使用這個虛擬環境。講師強調了這些步驟的重要性，以確保開發環境的正確設置，從而順利進行模型的開發和測試。

1.3. **Pylzma build tools (0:06:24)**
   - 介紹如何安裝Pylzma的編譯工具，該工具需要Visual Studio的Build Tools來正確編譯和運行。
這邊主要介紹了解決Pylzma編譯錯誤的方法，以及安裝PyTorch和CUDA的步驟。當安裝Pylzma庫時，可能會遇到編譯錯誤，這是因為該庫基於C++，需要Visual Studio Build Tools來進行編譯。講師建議前往Visual Studio的網站下載並安裝Build Tools，確保安裝“C++桌面開發”和“使用C++的Windows通用平台開發”這兩個工作負載。這些工具不僅對於當前項目有用，未來的項目也可能需要。

安裝Build Tools後，接下來講師介紹了如何安裝PyTorch和CUDA。使用特定的命令pip install torch來安裝PyTorch和CUDA擴展，這樣就可以利用GPU進行運算。講師還建議學員參考PyTorch的官方文檔來選擇合適的安裝命令，以便正確設置CUDA版本。這一部分的重點在於確保安裝和配置過程的正確性，以便在開發過程中順利利用GPU加速計算。

1.4. **Jupyter Notebook (0:08:58)**
   - 使用Jupyter Notebook作為主要的開發環境，設置和啟動Notebook的詳細步驟。

1.5. **Download wizard of oz (0:12:11)**
   - 下載《綠野仙蹤》的文本作為數據集，介紹如何從Project Gutenberg獲取開源書籍文本。

1.6. **Experimenting with text file (0:14:51)**
   - 處理和操作文本文件的實驗，包括讀取和簡單的數據清理。

1.7. **Character-level tokenizer (0:17:58)**
   - 介紹字符級的標記化工具（Tokenizer），用於將文本分解為最小單位。

1.8. **Types of tokenizers (0:19:44)**
   - 介紹不同類型的標記化工具，包括字符級、詞級和子詞級標記化的差異和應用場景。

1.9. **Tensors instead of Arrays (0:20:58)**
   - 解釋為什麼在機器學習中使用張量（Tensors）而非數組，介紹張量在PyTorch中的應用。

1.10. **Linear Algebra heads up (0:22:37)**
    - 對線性代數的基本概念進行簡要介紹，為後續的數學概念奠定基礎。

1.11. **Train and validation splits (0:23:29)**
    - 講解訓練集和驗證集的劃分方法及其重要性，避免模型過擬合。

1.12. **Premise of Bigram Model (0:25:30)**
    - 介紹Bigram模型的基本概念，解釋如何使用前一個單詞來預測下一個單詞。

1.13. **Inputs and Targets (0:26:41)**
    - 定義輸入和目標，講解如何從文本中生成訓練數據。

1.14. **Inputs and Targets Implementation (0:29:29)**
    - 實際實施輸入和目標生成的代碼，展示如何準備數據以進行模型訓練。

1.15. **Batch size hyperparameter (0:30:10)**
    - 設定批次大小（batch size）這一超參數，解釋其在訓練過程中的作用。

1.16. **Switching from CPU to CUDA (0:32:13)**
    - 介紹如何從CPU切換到CUDA，以利用GPU進行加速運算。

1.17. **PyTorch Overview (0:33:28)**
    - PyTorch基礎知識概述，包括基本的操作和功能。

1.18. **CPU vs GPU performance in PyTorch (0:42:49)**
    - 比較CPU和GPU在PyTorch中的性能差異，說明GPU在加速訓練中的優勢。

1.19. **More PyTorch Functions (0:47:49)**
    - 更多的PyTorch函數介紹，如`torch.stack`、`torch.multinomial`等。

1.20. **Embedding Vectors (1:06:03)**
    - 嵌入向量的介紹，說明其在自然語言處理中的重要性。

1.21. **Embedding Implementation (1:11:33)**
   - 具體實現嵌入向量的代碼，展示如何將單詞或字符映射到數字向量。

1.22. **Dot Product and Matrix Multiplication (1:13:06)**
   - 講解點積和矩陣乘法的基本概念及其在機器學習中的應用，特別是在神經網絡中的重要性。

1.23. **Matmul Implementation (1:25:42)**
   - 介紹矩陣乘法的具體實現方法，使用代碼演示如何在模型中應用這些數學運算。

1.24. **Int vs Float (1:26:56)**
   - 討論整數和浮點數的差異，並解釋為什麼在某些運算中選擇特定的數據類型。

1.25. **Recap and get_batch (1:29:52)**
   - 對前面的內容進行回顧，並介紹如何從數據集中提取批次數據以用於訓練。

1.26. **nnModule subclass (1:35:07)**
   - 介紹如何使用`nn.Module`子類來構建神經網絡模型，包括如何定義和使用自定義層。

1.27. **Gradient Descent (1:37:05)**
   - 講解梯度下降法，作為優化算法的一部分，詳細說明如何更新模型參數以減小損失函數。

1.28. **Logits and Reshaping (1:50:53)**
   - 解釋Logits的概念及其在模型輸出中的作用，並展示如何對數據進行重新塑形以適應模型需求。

1.29. **Generate function and giving the model some context (1:59:28)**
   - 介紹生成函數和給模型提供上下文信息的方法，這在文本生成應用中非常重要。

1.30. **Logits Dimensionality (2:03:58)**
   - 討論Logits的維度及其在不同模型結構中的影響。

1.31. **Training loop + Optimizer + Zerograd explanation (2:05:17)**
   - 詳細介紹訓練循環的實現，包括優化器的使用和`zerograd`的功能。

1.32. **Optimizers Overview (2:13:56)**
   - 優化器的概述，介紹不同類型的優化器及其特點。

1.33. **Applications of Optimizers (2:17:04)**
   - 討論不同優化器的應用場景，幫助學員選擇適合自己模型的優化算法。

1.34. **Loss reporting + Train VS Eval mode (2:18:11)**
   - 解釋如何報告訓練過程中的損失值，以及訓練模式和評估模式之間的區別。

1.35. **Normalization Overview (2:32:54)**
   - 正規化技術的概述，解釋其在神經網絡中的重要性和常用方法。

1.36. **ReLU, Sigmoid, Tanh Activations (2:35:45)**
   - 介紹常見的激活函數，包括ReLU、Sigmoid和Tanh，它們的特性及應用。

1.37. **Transformer and Self-Attention (2:45:15)**
   - Transformer模型及自注意力機制的介紹，講解其工作原理和優勢。

1.38. **Transformer Architecture (2:46:55)**
   - 詳細描述Transformer的架構設計，介紹各個組件的功能和相互關係。

1.39. **Building a GPT, not Transformer model (3:17:54)**
   - 說明如何構建GPT模型，而非標準Transformer，並討論這些差異。

1.40. **Self-Attention Deep Dive (3:19:46)**
   - 深入探討自注意力機制的細節，解釋其在語言模型中的應用。

1.41. **GPT architecture (3:25:05)**
   - 詳細介紹GPT模型的架構，包括其如何利用自注意力機制和Transformer塊來處理文本數據。

1.42. **Switching to Macbook (3:27:07)**
   - 講解如何在Macbook上設置開發環境，並與Windows進行對比，確保代碼在不同操作系統上運行一致。

1.43. **Implementing Positional Encoding (3:31:42)**
   - 說明位置編碼的實現方法，該技術在Transformer中用於引入序列信息。

1.44. **GPTLanguageModel initialization (3:36:57)**
   - 介紹如何初始化GPT語言模型，並解釋其內部結構和配置參數。

1.45. **GPTLanguageModel forward pass (3:40:52)**
   - 展示GPT模型的前向傳播過程，包括如何處理輸入數據和生成輸出。

1.46. **Standard Deviation for model parameters (3:46:56)**
   - 討論模型參數初始化時標準差的設置，對模型穩定性的影響。

1.47. **Transformer Blocks (4:00:50)**
   - 詳細介紹Transformer的基本組件——Transformer塊，包括自注意力和前饋神經網絡的結合。

1.48. **FeedForward network (4:04:54)**
   - 解釋前饋神經網絡在Transformer中的作用，以及其結構和運作方式。

1.49. **Multi-head Attention (4:07:53)**
   - 多頭注意力機制的深入講解，說明其如何提升模型的學習能力。

1.50. **Dot product attention (4:12:49)**
   - 講解點積注意力機制的數學原理，及其在自注意力中的應用。

1.51. **Why we scale by 1/sqrt(dk) (4:19:43)**
   - 解釋為什麼在計算點積注意力時需要進行1/sqrt(dk)的縮放，確保數值穩定性。

1.52. **Sequential VS ModuleList Processing (4:26:45)**
   - 比較Sequential和ModuleList在PyTorch中的用法及其優缺點。

1.53. **Overview Hyperparameters (4:30:47)**
   - 總結模型訓練中的關鍵超參數及其設置原則。

1.54. **Fixing errors, refining (4:32:14)**
   - 討論常見錯誤的修正方法，以及如何微調模型以提高性能。

1.55. **Begin training (4:34:01)**
   - 開始模型的訓練過程，展示訓練循環和損失函數的計算。

1.56. **OpenWebText download and Survey of LLMs paper (4:35:46)**
   - 介紹如何下載OpenWebText數據集，並討論與大型語言模型相關的文獻。

1.57. **How the dataloader/batch getter will have to change (4:37:56)**
   - 說明數據加載器和批次生成器的變化，適應不同數據集的需求。

1.58. **Extract corpus with winrar (4:41:20)**
   - 使用WinRAR解壓數據集，準備訓練所需的文本語料庫。

1.59. **Python data extractor (4:43:44)**
   - 使用Python編寫數據提取工具，將文本數據轉換為可訓練的格式。

1.60. **Adjusting for train and val splits (4:49:23)**
   - 根據不同數據集調整訓練和驗證集的分割比例。

1.61. **Adding dataloader (4:57:55)**
   - 添加數據加載器，實現批次數據的自動加載。

1.62. **Training on OpenWebText (4:59:04)**
   - 在OpenWebText數據集上進行模型訓練，展示實際操作過程。

1.63. **Training works well, model loading/saving (5:02:22)**
   - 討論訓練過程的進展，以及如何保存和加載訓練好的模型。

1.64. **Pickling (5:04:18)**
   - 使用Pickle庫保存Python對象，確保模型的持久化存儲。

1.65. **Fixing errors + GPU Memory in task manager (5:05:32)**
   - 修正訓練中的錯誤，並監控任務管理器中的GPU內存使用情況。

1.66. **Command line argument parsing (5:14:05)**
   - 介紹命令行參數解析，便於在腳本中靈活設置參數。

1.67. **Porting code to script (5:18:11)**
   - 將Notebook中的代碼轉換為Python腳本，以便更好地進行模型訓練和部署。

1.68. **Prompt: Completion feature + more errors (5:22:04)**
   - 討論提示詞和補全功能，及解決訓練過程中的進一步錯誤。

1.69. **nnModule inheritance + generation cropping (5:24:23)**
   - 講解`nn.Module`的繼承機制，及生成過程中的裁剪技術。

1.70. **Pretraining vs Finetuning (5:27:54)**
   - 比較預訓練和微調的概念及其應用場景。

1.71. **R&D pointers (5:33:07)**
   - 提供研究和開發過程中的建議，幫助學員進行實際應用。

1.72. **Outro (5:44:38)**
   - 課程總結和後續學習建議，激勵學員繼續探索和學習。



2.llm 應用內容:
 https://www.kdnuggets.com/run-an-llm-locally-with-lm-studio
3.deeplearning.ai短課程的學習紀錄,心得跟應用:
 https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/
4.醫療助手:
 醫療助手重新finetune
5.code助手:
 survey 以及初始化
6.RPA+LLM:
 survey 以及初始化
7.DL的內容跟實作(pytorch(8) ,tensorflow2(8) ,keras3(8),optuna(1),autokeras(1),yolo(1),unet(1)):
 pytorch入門
8.ML的內容跟實作(pandas,numpy,sk-learn):
9.音樂(4),語音(4),圖像(4),影片生成(4),具身智能(4)的內容,模型,框架跟實作:
10.目前較新或較為關鍵的論文,程式碼閱讀跟紀錄(一篇):
11.目前較新或較為熱門的生成式AI項目介紹,使用跟原理解讀(一篇):