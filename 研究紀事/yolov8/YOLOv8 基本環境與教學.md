source: 
https://hackmd.io/@luckychi/yolov8_simple_tutorial

key points:
* 建立基本環境
* 訓練模型
* 預測

1. 建立環境
	1. 下載CUDA及cuDNN
	2. 安裝python版本
	3. 安裝 pyTorch
2. YOLOv8模型訓練
	1. 準備圖片影像資料
	2. 分為train, valid, test資料夾
		* images (圖片)
		* labels (標註)
			* LabelImg
			* RoboFlow
3. 選擇模型
4. 下載模型
5. 訓練指令
`yolo detect train data=data.yaml model=yolov8n.pt epochs=100 imgsz=640 conf=0 device=cpu`
或
```python
from ultralytics import YOLO 
model = YOLO("yolov8n.yaml") model.train(data="data.yaml", 
	mode="detect", 
	epochs=100, 
	imgsz=640, 
	device="cpu"
)
```
其中device參數若未指定則會使用GPU進行訓練，device=0 使用第一張GPU卡，device=0,1使用2張卡來進行運算，device=cpu 使用CPU來運算，筆者測試的電腦顯示卡型號太舊，故使用CPU來進行訓練與預測