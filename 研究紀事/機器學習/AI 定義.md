---
title: What is artificial intelligence (AI)?
from:ＩＢＭ
ＵＲＬ：　https://www.ibm.com/topics/artificial-intelligence
---

### what's AI?
" It is the science and engineering of making intelligent machines, especially intelligent computer programs. It is related to the similar task of using computers to understand human intelligence, but AI does not have to confine itself to methods that are biologically observable." John McCarthy 2004
智慧機器/智慧電腦程式是關於電腦瞭解人類智慧的功能

Turing Test: "Can machines think?"  From there, he offers a test, now famously known as the "Turing Test", where a human interrogator would try to distinguish between a computer and human text response. Alan Turing 1950 (father of computer science)
圖寧測試於1950年由 Alan Turing提出，人類評審者是否可以分辨出是電腦或人為的反應

Stuart Russell and Peter Norvig in [Artificial Intelligence: A Modern Approach](https://aima.cs.berkeley.edu/) book
Human approach:
-   Systems that think like humans
-   Systems that act like humans

Ideal approach:
-   Systems that think rationally
-   Systems that act rationally

|        | 人類      | 合理性              |
|--------|------------|-----------------------|
|合理性| 系統可以像人一樣思考 | 系統思考的合理性 |
|行為性|系統可以像人一樣行為  |系統反應的合理性    |



Artificial intelligence is a field, which combines computer science and robust datasets, to enable problem-solving. It also encompasses sub-fields of machine learning and deep learning, which are frequently mentioned in conjunction with artificial intelligence. These disciplines are comprised of AI algorithms which seek to create expert systems which make predictions or classifications based on input data.
人工智慧是一個結合了計算機科學和資料集技術以解決問題的領域。還包括機器學習和深度學習的領域，這些領域經常與人工智慧一起提及。這些是由 AI 演算法組成，這些演算法試圖創建專家系統，根據輸入資料進行預測或分類。

### weak AI vs strong AI

**Weak AI**　（Narrow AI/Artificial Narrow Intelligence，ANI)
AI trained and focused to perform specific tasks. Weak AI drives most of the AI that surrounds us today.
AI 模型經過訓練並專注於執行特定任務。弱人工智慧是當今我們周圍的大部分人工智慧的應用情境。

**Strong AI** is made up of Artificial General Intelligence (AGI) and Artificial Super Intelligence (ASI), is a theoretical form of AI where a machine would have an intelligence equaled to humans; it would have a self-aware consciousness that has the ability to solve problems, learn, and plan for the future.
強人工智慧是人工智能的一種理論，其中機器將具有與人類相同的智慧；具有自我意識，具有解決問題、學習和規劃未來的能力。

### Applications and use cases for artificial intelligence
**Speech recognition** 語音辨識
Automatically convert spoken speech into written text.
**Image recognition** 圖形辨識
Identify and categorize various aspects of an image.
**Translation** 翻譯
Translate written or spoken words from one language into another.
**Predictive modeling** 預測模型
Mine data to forecast specific outcomes with high degrees of granularity.
**Data analytics** 資料分析
Find patterns and relationships in data for business intelligence.

### Artificial intelligence training models
**Supervised learning** is a machine learning model that maps a specific input to an output using labeled training data (structured data). In simple terms, to train the algorithm to recognize pictures of cats, feed it pictures labeled as cats.

**Unsupervised learning** is a machine learning model that learns patterns based on unlabeled data (unstructured data). Unlike supervised learning, the end result is not known ahead of time. Rather, the algorithm learns _from_ the data, categorizing it into groups based on attributes. For instance, unsupervised learning is good at pattern matching and descriptive modeling.

**Reinforcement learning** is a machine learning model that can be broadly described as “learn by doing.” An “agent” learns to perform a defined task by trial and error (a feedback loop) until its performance is within a desirable range. The agent receives positive reinforcement when it performs the task well and negative reinforcement when it performs poorly. An example of reinforcement learning would be teaching a robotic hand to pick up a ball.

### Machine learning
#machinrLearning

### AI Generated Content (AIGC) #AIGC
透過讓機器學習模型研究歷史數據的模式，且深度學習技術，進而去創造出一個全新生成的成品(文字、圖像、音訊、音樂、影片、程式碼、各種設計、行銷素材、3D模型等)。-   AIGC是一種透過生成模型自動產生內容的技術。

生成式人工智慧（Generative Artificial Intelligence）是指一種能夠自主生成具有某些特定屬性的內容的人工智慧技術。這些內容可以是文字、圖像、音訊、影片等等。生成式人工智慧的工作方式是通過對大量的訓練數據進行學習，然後使用這些數據來生成新的內容。其核心是通過對樣本數據進行學習，生成新的、與樣本數據相似的數據。生成式人工智慧不僅可以解決特定的問題，還可以生成全新的、原創的內容，這使得它在藝術、設計和創意領域等方面有著廣泛的應用前景。目前，生成式人工智慧已經在自然語言處理、圖像生成、音訊合成、文本摘要等領域取得了重要的進展。

生成式人工智慧的核心技術包括以下幾點
1.  神經網絡模型：生成式人工智慧的基礎是深度神經網絡模型，特別是對抗生成網絡（GAN）和變分自編碼器（VAE）。這些模型可以從大量的數據中學習如何生成新的、與原始數據相似的數據。
2.  機器學習算法：生成式人工智慧需要使用各種機器學習算法，如支持向量機（SVM）、隨機森林（Random Forest）、K最近鄰（KNN）等等，來幫助訓練神經網絡模型並改進其生成的效果。
3.  數據清理和預處理：生成式人工智慧需要處理大量的數據，這些數據通常是原始、噪聲多、數據不平衡等等問題，需要使用數據清理和預處理技術，如數據去重、標籤化、缺失值填補、正規化等等，來提高模型的訓練效果和生成效果。
4.  損失函數：生成式人工智慧需要使用損失函數來衡量模型生成的數據與真實數據之間的差異，通常使用的損失函數包括均方差（MSE）、交叉熵（Cross-Entropy）、KL散度（Kullback-Leibler Divergence）等等。
5.  模型優化和調參：生成式人工智慧需要使用各種優化算法，如梯度下降（Gradient Descent）、Adam、Adagrad等等，來提高模型的訓練效率和生成效果。同時也需要調整模型的參數，如學習率、隱藏層神經元數量、批量大小等等，來提高模型的性能。

CharGPT是一種生成式人工智慧模型，它是基於OpenAI開發的GPT（Generative Pre-trained Transformer）模型進行改進和優化得到的。CharGPT使用了GPT的基礎結構，同時加入了一些新的技術和優化方法，以實現更好的生成效果和效率。CharGPT的主要優勢是在自然語言生成方面，它能夠生成高質量、流暢、語法正確的文章、句子和段落等，並且能夠進行多樣性和有趣性的控制，甚至可以生成詩歌、故事等創意性內容。CharGPT的成功在很大程度上得益於其預訓練模型的優化和調整，以及對生成式人工智慧技術的深入理解和應用。CharGPT在自然語言處理、對話系統、文本生成等方面具有廣泛的應用前景，尤其是在AI寫作、智能客服、智能編輯等領域，可以大大提高生產效率和質量。

在CharGPT中，"pre-trained"（預訓練）是一種基於大量無標籤數據的學習方法。該方法是在大型文本數據集上訓練深度神經網絡模型，以學習自然語言的模式和結構，並從中獲取關於語言的知識。這些預訓練的模型可以通過微調來適應特定的任務。具體而言，CharGPT使用Transformer神經網絡架構，在大量文本數據集上進行了預訓練，學習了單詞、短語和句子之間的關係，以及上下文信息。這種方法使得模型能夠將先前學習到的知識運用到新的任務中，而不需要重新訓練整個模型。通過這種方式，CharGPT能夠在大量文本數據上學習自然語言的規則和模式，從而具有較高的生成能力和應用靈活性。該方法還具有可擴展性，可以在大型數據集上進行訓練，以提高模型的性能和效率。

**自然語言處理（Natural Language Processing，NLP）**
是一種涉及人工智能、計算機科學和語言學的交叉學科，旨在使計算機能夠理解、解讀、生成和操作人類自然語言的方式。NLP 技術可以幫助計算機處理和分析人類語言的結構、含義、情感和意圖，從而能夠自動地進行翻譯、摘要、語音識別、對話系統、情感分析、自然語言生成、文本分類等相關應用。NLP 技術在許多領域都有應用，包括自然語言處理界面、文本探勘、智能搜索、廣告選擇、機器翻譯、語音識別、自然語言生成、情感分析、智能對話系統、知識圖譜等。

ChatGPT是一種聊天機器人，它使用自然語言處理技術來理解和生成自然語言對話。它可以回答各種問題，提供幫助和建議，以及進行簡單的對話，使使用者可以與它進行互動。

Chatbot使用了多種技術來實現自然語言對話的能力。以下是其中一些主要技術：

1.  自然語言處理（Natural Language Processing, NLP）：用於解析人類語言，理解和處理用戶的語言輸入。
2.  語音辨識（Speech Recognition）：將聲音轉換為文本，以便聊天機器人進一步處理。
3.  語音合成（Text-to-Speech）：將機器人的回答轉換為自然語言的語音輸出。
4.  機器學習（Machine Learning）：通過訓練模型來改進機器人的回答，並使其能夠更好地處理自然語言輸入。
5.  語料庫（Corpus）：聊天機器人需要大量的對話語料庫，以便訓練模型和改進回答。
6.  語意理解（Natural Language Understanding, NLU）：用於理解自然語言的意義和意圖。
7.  對話管理（Dialogue Management）：管理對話流程，選擇回答並控制對話的進展。
8.  API（Application Programming Interface）：用於連接不同的技術組件，以實現聊天機器人的功能。