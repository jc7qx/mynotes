ROC(receiver operating characteristic, ROC)曲線用於表示二元分類器的效能。ROC表示TPR與FPR之間的關係(TPR = true positive rate，FPR = false positive rate)，TPR 為 sensitivity，FPR為 - specificity 或 true negative rate。

繪製方式：
```python
from sklearn.metrics import roc_curve
fpr, tpr, thresholds = roc_curve(y, y_scores, pos_label=2)
plot(fpr, tpr)
roc_auc_score(y, y_score)
```

計算曲線下方的面積，產生一個介於 0~1 的數值，只要等於 0.5 就是跟隨機猜測一樣，代表此分析模型沒有預測價值；若大於 0.5 代表猜測是正向的，而小於 0.5 代表猜測的方向恰好相反；而 1 或 0 代表全部辨識正確或全部辨識錯誤。