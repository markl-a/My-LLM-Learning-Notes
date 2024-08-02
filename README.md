# 我的 AI工程師相關筆記

## TODO

 - [ ] 30天的鐵人賽更新
 - [ ] Deeplearning.ai 短課程的學習紀錄
 - [ ] 醫療助手
 - [ ] Code 助手
 - [ ] RPA + LLM


# 目錄

- [簡介](#簡介)
- [算法與資料結構](#算法與資料結構)
- [從AI到LLM基礎](#從ai到llm基礎)
- [深入LLM模型工程與LLM運維](#深入llm模型工程與llm運維)
- [LLM應用工程](#llm應用工程)
- [相關的更新Blog](#相關的更新blog)
- [DeepLearningAI短課程學習紀錄](#deeplearningai短課程學習紀錄)

![cover](./img/aie_cover.png)

## 簡介

這個 Notes 主要是我自己對於AI工程師相關的知識以及技能的了解與整理，主要的目錄是根據[llm-course](https://github.com/mlabonne/llm-course)進行延伸以及擴展，並加上一些AI, ML, DL以及一些資料分析相關的必備知識與技能整理。

不過目前會是以LLM為主，除了我之前就弄過的相關內容之外，其他的內容會是必須的才會被添加。

## 算法與資料結構

這邊主要會是我算法提練習的紀錄以及閱讀的心得，因為我不是大學教授或專家等級的，所以目前難免會有點錯誤。

之後補上專業的相關內容以及實作心得。

我算法題練習的倉庫:[LeetcodePractice](https://github.com/markl-a/LeetcodePractice)

## 從AI到LLM基礎

這邊主要是根據 LLM course 上面的目錄為基礎的加深以及補強。

主要內容為數學基礎,資料分析跟處理,機器學習,深度學習中的 NLP 以及 CV 和 MLOps

(為原內容再加深之外再加上CV 跟 MLOps等工作上可能會用到的內容)

之後再新增[ChatGPT for Data Analytics : Full Course](https://youtu.be/uhyMqbZI6rM?si=ebSO8H07ELUZn57z)的學習紀錄跟內容。

<details>
<summary>點擊以打開詳細內容</summary>

![從AI到LLM基礎](./img/從AI到LLM基礎.png)

### 1. 機器學習數學基礎

在掌握機器學習之前，了解支撐了這些演算法的基本數學概念非常重要。不過其實大概看這三個影片課程大概就可以了，這一系列的影片教學有教學跟實作，其他的就有興趣再看。

1.線性代數:[Linear Algebra for Machine Learning](https://www.youtube.com/playlist?list=PLRDl2inPrWQW1QSWhBU0ki-jq_uElkh2a)

這對於理解許多演算法至關重要，尤其是深度學習中使用的演算法。關鍵概念包括向量、矩陣、行列式、特徵值和特徵向量、向量空間和線性變換。
  
2.微積分:[Calculus for Machine Learning ](https://www.youtube.com/playlist?list=PLRDl2inPrWQVu2OvnTvtkRpJ-wz-URMJx)

許多機器學習演算法涉及連續函數的最佳化，這需要了解導數、積分、極限和級數。另外多變量微積分和梯度的概念也很重要。
 
3.機率與統計:[Probability for Machine Learning ](https://www.youtube.com/playlist?list=PLRDl2inPrWQWwJ1mh4tCUxlLfZ76C1zge)

這些對於理解模型如何從數據中學習並做出預測至關重要。 關鍵概念包括機率論、隨機變數、機率分佈、期望、變異數、協方差、相關性、假設檢定、信賴區間、最大似然估計和貝葉斯推理。

<details>
<summary>點擊以打開可延伸的閱讀以及參考連結：</summary>
  
</br>
可延伸的閱讀以及參考：

</br>

電子書：

- [深度學習中的數學](https://github.com/jash-git/Jash-good-idea-20200304-001/blob/master/CN%20AI%20book/%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0%E7%9A%84%E6%95%B0%E5%AD%A6.pdf)

- [深度學習基礎以及數學原理](https://github.com/HaoMood/File/blob/master/%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0%E5%9F%BA%E7%A1%80%E5%8F%8A%E6%95%B0%E5%AD%A6%E5%8E%9F%E7%90%86.pdf)

其他相關連結：

- [動手深度學習-中的預備知識那章](https://zh-v2.d2l.ai/d2l-zh-pytorch.pdf)
- [動手深度學習這本書也能讓一般人大致上了解深度學習的運作](http://zh.gluon.ai/chapter_introduction/deep-learning-intro.html)
- [Blog- 深度學習(Deep Learning)-數學整理](https://dysonma.github.io/2021/01/27/%E6%B7%B1%E5%BA%A6%E5%AD%B8%E7%BF%92-Deep-Learning-%E6%95%B8%E5%AD%B8%E6%95%B4%E7%90%86/)
- [Blog- 機器/深度學習-基礎數學篇(一)(內容跟上面雷同)](https://chih-sheng-huang821.medium.com/%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-%E5%9F%BA%E7%A4%8E%E6%95%B8%E5%AD%B8%E7%AF%87-%E4%B8%80-1c8337179ad6)
- [我是如何學習深度學習中的數學的？(可參考方法)](https://yanwei-liu.medium.com/%E6%88%91%E6%98%AF%E5%A6%82%E4%BD%95%E5%AD%B8%E7%BF%92%E6%B7%B1%E5%BA%A6%E5%AD%B8%E7%BF%92%E4%B8%AD%E7%9A%84%E6%95%B8%E5%AD%B8%E7%9A%84-a26eee623638)

- [深度學習經典(花書)](https://github.com/ytin16/awesome-machine-learning-1/blob/master/Deep-Learning%E8%8A%B1%E4%B9%A6-%E3%80%8A%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0%E3%80%8B-%E4%B8%AD%E6%96%87%E7%89%88.pdf)

- [深度學習經典(花書)中的數學推導](https://github.com/MingchaoZhu/DeepLearning)

- [繁中的深度學習中的數學相關資料](https://hackmd.io/@changken/rkukooSGS#%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%E5%8F%8A%E6%B7%B1%E5%BA%A6%E5%AD%B8%E7%BF%92%E7%9A%84%E8%B3%87%E6%96%99)
- [用 Python 學微積分](https://ryancheunggit.gitbooks.io/calculus-with-python/content/01Functions.html)
- [機器學習的數學基礎：矩陣篇](http://www.hahack.com/math/math-matrix/)
- [機器學習的數學基礎：向量篇](http://www.hahack.com/math/math-vector/)
- [機器學習的數學基礎：線性代數進階篇](http://www.hahack.com/math/math-linear-algebra-graded/)
- [Python for Probability, Statistics, and Machine Learning](https://github.com/unpingco/Python-for-Probability-Statistics-and-Machine-Learning)
- [Think Bayes](https://greenteapress.com/wp/think-bayes/)
- [統計分佈 方開泰教授 王元教授](http://item.jd.com/12019664.html)
- [概率論與數理統計 陳希孺教授](https://www.amazon.cn/dp/B073LBYPZ4/ref=sr_1_1?ie=UTF8&qid=1546071311&sr=8-1&keywords=陈希儒)
- [Linear Regression in Python with Scikit-Learn](https://stackabuse.com/linear-regression-in-python-with-scikit-learn/)
- [線性代數自學課程，國內外學習資源](https://selflearningsuccess.com/linear-algebra-courses/#Mathematics_for_Machine_Learning_Linear_Algebra): 本文彙整國內外線性代數自學課程，提供給規劃學習線性代數的朋友們參考。
- [3Blue1Brown - 線性代數的本質](https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab): 此系列的影片介紹幾何相關的概念
- [StatQuest with Josh Starmer - 統計基礎知識](https://www.youtube.com/watch?v=qBigTkBLU6g&list=PLblh5JKOoLUK0FLuzwntyYI10UQFUhsY9): 為許多統計概念提供簡單明了的解釋。
- [Aerin女士的AP統計直觀理解](https://automata88.medium.com/list/cacc224d5e7d): 提供每個機率分佈背後的Medium文章清單。
- [沉浸式線性代數](https://immersivemath.com/ila/learnmore.html): 線性代數的另一種圖像化詮釋.
- [Khan Academy - 線性代數](https://www.khanacademy.org/math/linear-algebra): 非常適合初學者，因為它以非常直觀的方式解釋了概念。
- [Khan Academy - 微積分](https://www.khanacademy.org/math/calculus-1): 一門涵蓋微積分所有基礎知識的互動課程。
- [Khan Academy - 機率與統計](https://www.khanacademy.org/math/statistics-probability): 以易於理解的格式提供材料。
---
</details>

### 2. AI簡介

- **AI大致的歷史跟介紹**:
    - [人工智慧史-維基百科](https://zh.wikipedia.org/zh-tw/%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD%E5%8F%B2)
    - [人工智慧到生成式AI的發展(2010 ~2024)]()
- **AI課程推薦**:

    -  這邊我推薦大致可以通過這個課程入門AI:
        [Harvard CS50’s Artificial Intelligence with Python – Full University Course](https://youtu.be/5NgNicANyqM?si=yTbD-6wCbPYzsCVL)

        下面的課程在學完之後也可以參考下，不過基本上面那個應該就足夠了。

        [General Intro | Stanford CS221: Artificial Intelligence: Principles and Techniques (Autumn 2021)](https://youtu.be/ZiwogMtbjr4?si=1KUL6JkiQE7qyiju)

        [MIT 6.034 Artificial Intelligence, Fall 2010](https://youtu.be/TjZBTDzGeGg?si=9qV18PmDo9i63Qxsu)

        可以從上面的內容發現，隨著時間的演變，這些基礎學科的內容著重的部分其實也有很多改變，所以要學的話大概也就學自己需要的就可以了。

### 3. 機器學習與Python

Python 是一種強大而靈活的程式語言，由於其可讀性、一致性和強大的資料科學庫生態系統，特別適合機器學習。


- **Python基礎**: Python程式設計需要很好地理解基本語法、資料類型、錯誤處理和物件導向程式設計。
    -  推薦閱讀,應用-[Into Python in one video](https://www.giraffeacademy.com/programming-languages/python/in-one-video/)
- **資料科學函式庫**: 包括熟悉用於數值運算的 NumPy、用於資料操作和分析的 Pandas、用於資料視覺化的 Matplotlib 和 Seaborn。
    -  推薦閱讀,應用-[Visualization Curriculum](https://uwdata.github.io/visualization-curriculum/intro.html)
    -  推薦閱讀,應用-[Python資料科學分享－3.資料視覺化(1)](https://asyncfor.com/jupyter/python/data%20science/2020/05/22/data-viz-1.html)
    -  推薦閱讀,應用-[Python資料科學分享－3.資料視覺化(2)](https://asyncfor.com/jupyter/python/data%20science/2020/05/29/data-viz-2.html)
- **資料預處理**: 這涉及特徵縮放和標準化、處理缺失資料、異常值檢測、分類資料編碼以及將資料拆分為訓練集、驗證集和測試集。
    -  推薦閱讀,應用- 概覽[[資料分析&機器學習] 第2.4講：資料前處理(Missing data, One-hot encoding, Feature Scaling)](https://medium.com/jameslearningnote/%E8%B3%87%E6%96%99%E5%88%86%E6%9E%90-%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-%E7%AC%AC2-4%E8%AC%9B-%E8%B3%87%E6%96%99%E5%89%8D%E8%99%95%E7%90%86-missing-data-one-hot-encoding-feature-scaling-3b70a7839b4a)
    -  推薦閱讀,應用-[Python資料科學分享—2.資料處理](https://asyncfor.com/jupyter/python/data%20science/2020/05/15/data-etl.html)
    -  推薦閱讀,應用-[[機器學習筆記]數據預處理](https://doremi31618.medium.com/%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%E7%AD%86%E8%A8%98-%E6%95%B8%E6%93%9A%E9%A0%90%E8%99%95%E7%90%8601-ae90853978da)
- **機器學習函式庫**: 熟練使用 Scikit-learn（一個提供多種監督和非監督學習演算法的函式庫）至關重要。了解如何實現線性迴歸、邏輯迴歸、決策樹、隨機森林、k 最近鄰 (K-NN) 和 K 均值聚類等演算法非常重要。PCA 和 t-SNE 等降維技術也有助於視覺化高維度資料。
    -  推薦閱讀,應用(裡面有ipynb)-[Introducing Scikit-Learn](https://doremi31618.medium.com/%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%E7%AD%86%E8%A8%98-%E6%95%B8%E6%93%9A%E9%A0%90%E8%99%95%E7%90%8601-ae90853978da)
    - 推薦閱讀,應用(裡面有ipynb)-[Python 資料科學手冊(裡面有ipynb ,colab)](https://jakevdp.github.io/PythonDataScienceHandbook/):
      免費的數位書籍，是學習 pandas、NumPy、Matplotlib 和 Seaborn 的絕佳資源。    

📚 資源：

- [Real Python](https://realpython.com/): 綜合資源，包含初學者和進階 Python 概念的文章和教學。
- [freeCodeCamp - 學習 Python](https://www.youtube.com/watch?v=rfscVS0vtbw): 長影片，完整介紹了 Python 中的所有核心概念。
- [Python 資料科學手冊](https://jakevdp.github.io/PythonDataScienceHandbook/): 免費的數位書籍，是學習 pandas、NumPy、Matplotlib 和 Seaborn 的絕佳資源。
- [freeCodeCamp - 適合所有人的機器學習](https://youtu.be/i_LwzRVP7bg): 為初學者介紹不同的機器學習演算法。
- [Udacity - 機器學習簡介](https://www.udacity.com/course/intro-to-machine-learning--ud120): 免費課程，涵蓋 PCA 和其他幾個機器學習概念。

---
### 3. 神經網絡跟深度學習

- **基礎知識**: 這包括理解神經網路的結構，例如層、權重、偏差和激活函數（sigmoid、tanh、ReLU 等）
    - [3Blue1Brown - 什麼是神經網路？](https://www.youtube.com/watch?v=aircAruvnKk): 該影片直觀地解釋了神經網路及其內部運作原理。
- **深度學習框架**: 目前是在深度學習框架方面還是 Pytorch 最熱門，但是有些老應用跟某些 Google 相關的應用仍還是使用 Tensorflow 。假如要入門的話建議下面四個連結找一個入門並實作一個應用即可。
    - [freeCodeCamp - 深度學習速成課程](https://www.youtube.com/watch?v=VyWAvY2CF9c): 此影片簡潔地介紹了深度學習中所有最重要的概念。
    - [動手深度學習官網](https://zh.d2l.ai/chapter_linear-networks/index.html)
    - [動手深度學習包含 tensorflow,pytorch 程式碼的教學，不過要自己debug](https://zh-v2.d2l.ai/d2l-zh.zip)
    - [pytorch官網教學](https://pytorch.org/tutorials/beginner/basics/intro.html):建議學習路線: Introduction to PyTorch ->Image and Video ,Audio ,Text 按需學習，只學需要的就好(建議只先選一個)。
    - [tensorflow 官網教學](https://www.tensorflow.org/tutorials?hl=zh-tw): Begginner -> Adanced(也是建議按需學習)
- **訓練與最佳化**: 熟悉反向傳播和不同類型的損失函數，例如均方誤差 (MSE) 和交叉熵。了解各種最佳化演算法，例如梯度下降、隨機梯度下降、RMSprop 和 Adam。
神經網路是許多機器學習模型的基本組成部分，特別是在深度學習領域。為了有效地利用它們，全面了解它們的設計和機制至關重要。
- **過度擬合**: 了解過度擬合的概念（模型在訓練資料上表現良好，但在未見過的資料上表現不佳）並學習各種正則化技術（dropout、L1/L2 正則化、提前停止、資料增強）來防止過度擬合。
- **實作多層感知器 (MLP)**: 使用 PyTorch 建構 MLP，也稱為全連接網路。
  
📚 其他資源:
- [Patrick Loeber - PyTorch 教學](https://www.youtube.com/playlist?list=PLqnslRFeH2UrcDBWF5mfPGpqQDSta6VK4): 為初學者學習 PyTorch 的系列影片。

---

### 4. 自然語言處理(NLP)

NLP 是人工智慧的一個令人著迷的分支，它彌合了人類語言和機器理解之間的差距。從簡單的文字處理到理解語言的細微差別，NLP 在翻譯、情緒分析、聊天機器人等許多應用中發揮著至關重要的作用。

- **文字預處理**: 學習各種文字預處理步驟，例如分詞（將文字分割成單字或句子）、詞幹擷取（將單字還原為其詞根形式）、詞形還原（與詞幹擷取類似，但考慮上下文）、停用詞刪除等。
- **特徵提取技術**: 熟悉將文字資料轉換為機器學習演算法可以理解的格式的技術。主要方法包括詞袋 (BoW)、詞頻-逆文檔頻率 (TF-IDF) 和 n-gram。
- **詞嵌入**: 詞嵌入是一種詞表示形式，允許具有相似意義的詞具有相似的表示形式。主要方法包括 Word2Vec、GloVe 和 FastText。
    - [Jay Alammar - The Illustration Word2Vec](https://jalammar.github.io/illustrated-word2vec/):了解著名 Word2Vec 架構的一個好材料。
- **遞歸神經網路 (RNN)**: 了解 RNN 的工作原理，RNN 是一種設計用於處理序列資料的神經網路。探索 LSTM 和 GRU，這兩種能夠學習長期依賴關係的 RNN 變體。
    - [Jake Tae - PyTorch RNN from Scratch](https://jaketae.github.io/study/pytorch-rnn/): 在 PyTorch 中實用且簡單地實作 RNN、LSTM 和 GRU 模型。
    - [colah's blog - Understanding LSTM Networks](https://colah.github.io/posts/2015-08-Understanding-LSTMs/): 一篇更理論性的 LSTM 網路文章。
- **基於 Transformer 跟預訓練模型的 NLP**: 由於基於類 Transformer 的模型能處理之前其他 經典 NLP 模型處理的任務，並且大部分任務能做得更好，所以我覺得這是必學的一部分。
    - [NLP course from huggingface](https://huggingface.co/learn/nlp-course/chapter1/1)

📚 Resources:
- [RealPython - NLP with spaCy in Python](https://realpython.com/natural-language-processing-spacy-python/): 有關 Python 中用於 NLP 任務的 spaCy 函式庫的詳細指南。
- [Kaggle - NLP Guide](https://www.kaggle.com/learn-guide/natural-language-processing):一些 notebooks 和資源，用於 Python 中 NLP 的實踐解釋。 

</details>

<br>


## 深入LLM模型工程與LLM運維

這邊是從模型本身的架構到模型運作整個流程的必備知識跟技能。

大致如下：

1.模型了解與選擇

2.資料集收集,準備

3.模型訓練,微調(lora,Qlora ..),對齊(RLHF,DPO..)

4.模型優化和壓縮

5.模型部署以及系統整體流程維護

<details>
<summary>點擊以打開詳細內容</summary>

![roadmap_scientist](./img/roadmap_scientist.png)

</details>

<br>


## LLM應用工程

這邊主要就是 LLM 部署, Agent, RAG,這類的知識與內容。

這邊主要新增的內容是 LLM 結合自動化以及把 LLM 當作 API 結合到實際的應用中。

例如：在解析完程式碼之後，把輸出的程式碼插入到編輯器中。或者將LLm融合到類似UIpath的運作中。

<details>
<summary>點擊以打開詳細內容</summary>

![roadmap_engineer](./img/roadmap_engineer.png)

</details>

## 相關的更新Blog
主要是鐵人賽的備份跟之後每次更新的具體內容

## DeepLearningAI短課程學習紀錄
這邊就是每個Deeplearning.ai 的短課程，我今年應該會把短課程以及相關的生成式AI課程補上。
