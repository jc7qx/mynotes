分類預測問題(Classification Prediction Problem)是由演算法將資料(Observation)依特性指定到特定類別(Class)，經由演算法計算可以產生一個預測類別。執行分類預測，必須先蒐集歷史案例(Example)，一個案例包括某問題領域的觀察資料(又稱input)及類別標籤(class label)，問題領域的觀察資料由特徵屬性(features)組成，類別具有限、離散、固定特性。例如，根據個案的特徵屬性可以預測再犯與否(二元分類)。分類問題大略可分為「二元分類」及「多元分類」問題。
* 二元分類問題將案例歸為二類
* 多元分類問題將案例歸為三類以上

執行分類預測，必須先蒐集歷史案例以便建立訓練資料集(training data set)，訓練資料集中的每一筆資料包括觀察到的特徵屬性值(input)及確定的分類標籤(output)。

> A training dataset is a number of examples from the domain that include both the |input data (e.g. measurements) and the output data (e.g. class label).

訓練資料集的資料數量影響分類演算法的效能，事實上，分類模型是根據訓練資料集中的案例經由學習演算法演化出分類規則。具體言之，訓練資料集幫助建立模型及調整模型參數，之後，當新的未知分類的案例輸入時可藉以預測分類。除了訓練資料集的資料數量外，每一個類別的資料數量也會影響分類預測模型的效能，每個類別所包含的資料數量差異很大將影響分類模型預測準確度，稱之為不平衡分類([[Imbalanced Classification]])。


