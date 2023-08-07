source: https://juejin.cn/post/7187726947252699192

[[YOLOv8]] 是ultralytics 公司在2023 年1月10 號開源的YOLOv5 的下一個重大更新版本，目前支持圖像分類、物體檢測和實例分割任務，YOLOv8 是一個[[SOTA 模型]]，它建立在以前YOLO 版本的成功基礎上，並引入了新的功能和改進，以進一步提升性能和靈活性。具體創新包括一個新的[[骨幹網絡]]、一個新的[[Ancher-Free 檢測頭]]和一個新的[[損失函數]]，可以在從CPU 到GPU 的各種硬件平台上運行。

**官方開源地址：** **[github.com/ultralytics…](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fultralytics%2Fultralytics "https://github.com/ultralytics/ultralytics")**
**MMYOLO 開源地址：** **[github.com/open-mmlab/…](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fopen-mmlab%2Fmmyolo%2Fblob%2Fdev%2Fconfigs%2Fyolov8%2F "https://github.com/open-mmlab/mmyolo/blob/dev/configs/yolov8/")**

[[模型結構]]設計
[[損失函數]]計算
[[訓練數據]]增強
[[訓練策略]]
[[模型推理]]過程
[[特徵圖]]可視化

#yolov8 