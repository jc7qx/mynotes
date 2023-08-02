#roc_auc #roc_auc_curve
ROC(receiver operating characteristic, ROC)曲線用於表示二元分類器的效能。ROC表示TPR與FPR之間的關係(TPR = true positive rate，FPR = false positive rate)，TPR 為 sensitivity，FPR為 - specificity 或 true negative rate。

繪製方式：
```python
from sklearn.metrics import roc_curve
import matplotlib.pyplot as plt

def plot_roc_curve(true_y, y_proba):
    """
    plots the roc curve based of the probabilities
    """

    fpr, tpr, thresholds = roc_curve(true_y, y_prob)
    plt.plot(fpr, tpr)
    plt.xlabel('False Positive Rate')
    plt.ylabel('True Positive Rate')
```
* `roc_curve(y_true, y_score)`
	* Compute Receiver operating characteristic (ROC)
	* **y_true**: True binary labels. labels are either {-1, 1} or {0, 1}
	* **y_score**: Target scores, probability estimates of the positive class
	* **pos_label**: int, float, bool or str, default=None. The label of the positive class. When `pos_label=None`, if `y_true` is in {-1, 1} or {0, 1}, `pos_label` is set to 1, otherwise an error will be raised.
	* **returns**: <mark style="background: #FF5582A6;">fpr</mark>, <mark style="background: #FF5582A6;">tpr</mark>, <mark style="background: #FF5582A6;">thresholds</mark>

`roc_auc_score(y_true, y_score)` 
* 計算ROC_AUC曲線下方的面積，產生一個介於 0~1 的數值，只要等於 0.5 就是跟隨機猜測一樣，代表此分析模型沒有預測價值；若大於 0.5 代表猜測是正向的，而小於 0.5 代表猜測的方向恰好相反；而 1 或 0 代表全部辨識正確或全部辨識錯誤。

[Receiver operating characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) wikipedia
[roc_auc_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html) scikit learn
[roc_auc curve](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_curve.html#sklearn.metrics.roc_curve) scikit learn

