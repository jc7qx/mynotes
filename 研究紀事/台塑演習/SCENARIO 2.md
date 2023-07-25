# Human Machine Interface Hijack: On-screen Suspected Activity
人機介面操作員發現螢幕上滑鼠游標運作不正常，似乎受到其他元件所控制，有異於正常情況，或有固定行為模式。

討論：有甚麼人會從本機或遠端操控人機介面？

團隊：工程人員、作業人員、ICS資通安全、網管人員

防護：網管、流程控制、作業人員循作業規定回報事件

偵測：遠端存取事件監控（外部->內部，內部->內部-RDP），多因子驗證，ICS DMZ使用 [[jump box]] (Purdue Level 3, etc.)

應變：<mark style="background: #FF5582A6;">關閉遠端存取</mark>，經由<mark style="background: #FF5582A6;">嵌入式HMI</mark>([[embedded HMIs]])執行工控系統作業 , 調查NSM網路通訊模式，啟動<mark style="background: #FF5582A6;">島嶼隔離</mark>將ICS與網際網路與IT隔離(enable [[islanding]] from Internet, IT), etc.
> 島嶼隔離常見應用在網路安全中，將受感染或遭受威脅的設備或區域與其他部分隔離，防止威脅擴散到整個網路。限制損害範圍並增強整體網路安全性。



