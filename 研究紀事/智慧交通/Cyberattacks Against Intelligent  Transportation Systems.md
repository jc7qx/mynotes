[National ITS Architecture Security]([National ITS Architecture.pdf](file:///E:/Research/ITS%E8%B3%87%E5%AE%89/National%20ITS%20Architecture.pdf))
[FRAME](FRAME)
Japanese ITS System Architecture
[MITRE ATT&CK](https://attack.mitre.org/)
[Transportation Systems Sector Cybersecurity Framework Implementation Guidance](https://www.cisa.gov/sites/default/files/publications/tss-cybersecurity-framework-implementation-guide-2016-508v2_0.pdf)

6 ITS 應用子系統 (A&S)

車輛（如汽車、卡車、巴士…等）是運輸系統的基本元件，車輛配置網際網路及具備無線區域網路，使它可與其他車輛分享網際網路，更進階的連結車可以運用各種技術，如光學雷達、雷達、GPS、及3D攝影機，偵測環境及進行無人導航。

Roadway Reporting
road operators need to constantly monitor traffic and current roadway conditions using an extensive array of cameras and sensors that are strategically placed all across the roadway and which sends back data real-time to the control center, including bus lane cameras, speed cameras, roadside weather stations, and vehicle detection systems.

Traffic Flow Controls
Road operators monitor traffic and roadway conditions in real-time and use gathered data to manage traffic flow using various flow-control mechanisms including traffic signal control systems, railway crossing barriers, dynamic message signs, and automated toll collection systems.

Payment Applications and Systems
increase their revenue stream while reducing costs including RFID payments/tags, kiosk payment machines, and e-ticket applications.


Management Applications and Systems
ITS nerve centers host, monitor, and operate the management systems controlling ITS. including streetlight controls, disaster management, data and data storage management, emergency vehicle management, and traffic and congestion management.

Communications Applications and Systems
Data is used for making traffic flow efficient, improving road safety, increasing revenue, and reducing ecological and environmental impact, among other uses. Data is also consumed by the users of ITS services to improve their transit options and experiences. Examples include: smart apps, social media, websites, and road obstacle and accident alerts.

11 Real-World ITS Attacks

攻擊者分類

------
ITS攻擊向量

實體攻擊
* 實體連結到曝露的端口，如USB、PS2、序列型端口...等
* 在裝置上使用暴力法或猜測密碼憑據
* 刺探裝置與後端間的網路傳輸
* 掃描保護/關閉的網路以探究網路架構
* 在被破壞的ITS裝備/系統上刪除檔案
* 盜取韌體以回復密碼憑據及組態
* 使用曝露的線路/電纜進行中間人攻擊(Man-in-the-Middle)以攔截資料
* 實體篡改裝置偷取/破壞資料，修改裝置
* 連接一個可移除的儲存裝置，藉由安裝惡意程式
* 傳送不正常的指令到控制及後端伺服器
* 中間人攻擊至後端伺服器的通訊及傳送假資料
* 選取一個ITS裝備作為可信任的進入企業網路的端點
* 運用軟體、硬體、通信協定、作業系統的漏洞弱點
* 可信任的操作員使用權限篡改及破壞裝置

無線通訊攻擊(V2V, V2I, I2I無線通訊將給予攻擊者機會)
* V2V, V2I, I2I欺騙訊息傳送影響ITS系統各個層面
* 刺探無線傳輸，如使用車輛的wifi
* 遠端傳送及安裝惡意軟體
* 對於擾亂作業的無線傳輸的電子干擾
* 無線傳輸的中間人攻擊以攔截及/或更改資料
* 運用軟體、硬體、通信協定、作業系統的漏洞弱點
* 運用車輛wifi作為控制器區域網路匯流排(CAN)進入點，再進入車輛線上診斷器(OBD)，遠程訊息處理控制單元(TCU)，及車輛上資訊單元（IVI)
* 經由受損的CAN匯流排對於車輛控制進行遠端劫持
* 在車輛資訊系統中安裝惡意的第三方應用程式
* 經由安裝在與車輛wifi連結的電話上的惡意應用程式攻擊
* 對車輛安全系統的電子干擾，如雷達，聲納等

網路攻擊(藉由網路產生的資安攻擊，如暴露於Internet連結的IoT，IoT搜尋引擎-[shodan](https://www.netadmin.com.tw/netadmin/zh-tw/technology/2CD1DAA23ECE4C389F0E79EC46396676))
* 識別與濫用裝備的錯誤配置
* 利用舊軟體與硬體的漏洞弱點 
* 發現與濫用遠端系統，如使用shodan搜尋引擎
* 在系統安裝惡意/間諜程式
* 複雜的國家資助目標定位攻擊或進階持續性威脅(APT)
* 上傳及安裝惡意韌體
* 社會工程攻擊，如魚叉式網路釣魚
* 在網際網路暴露的ITS架構及後端伺服器發動DDoS攻擊
* 運用軟體、硬體、通信協定、作業系統的漏洞弱點
* 暴力法解密及濫用弱身份驗證機制
* 經由廣告、橫幅、假廣告注入惡意程式腳本
* SQL指令注入攻擊(SQL Injection Attacks)
* 跨站腳本攻擊(XSS Attacks)
* 連線劫持攻擊(Session hijack Attacks)
* DNS欺騙及劫持攻擊
* 水坑攻擊(watering hole attacks)
* 內網滲透(pass the hash attacks)
* 票證傳遞攻擊(pass-the-ticket attacks)
* 傳送不正常指令給控制器及後端伺服器
* 選取一個ITS裝備作為可信任的進入企業網路的端點
* 可信任的操作員使用權限篡改及破壞裝置
* 破壞一個第三方合約者電腦，並經由這些受感染的機器進入企業網路運作

-----
VANET攻擊
[[車輛隨意網路(VANET)]]將是ITS的核心技術，用於連結車輛及未來的自主車輛。VANET由智慧車輛及道路單元(RSU)所組成，RSU藉由不穩定的無線媒介進行通訊。由於隨意特性，VANET將可能遭受攻擊而迫害道路安全性，特別是當車輛根據VANET資料執行關鍵的駕駛決策時。以下根據Fatih Sakiz及evil Sen的論文，綜整以下針對VANET的攻擊向量
	* Sybil Attack：在此攻擊中，每一個節點(車輛)假裝有多個識別(identity)，造成網路中其他車輛無法驗證接收的資料，是從一輛或多輛車輛而來。攻擊者的目的在於根據他的想法來塑造網路。Sybil攻擊是對VANET最危險的一種攻擊，相當難以偵測。
	* DDoS Attack：發送超過系統可以處理能量的工作要求，造成系統癱瘓及不可用。在VANET，攻擊者嘗試關閉由RSU所組成的網路，停止車輛與RSU之間的通訊。
	* Blackhole Attack：攻擊者節點在隨意協力網路中操控其他節點使資料封包傳遞時通過攻擊者節點，攻擊者藉以丟棄資料封包造成網路中通訊中斷，致使其他的車輛無法接收重要的道路資訊。
	* Wormhole Attack：二個以上的受損節點依據他們所知的到任何目的地的最短路徑假通知，盡可能地發出路由要求。攻擊者的目的要修改網路的邏輯拓撲使所有路由要求經過他們，以致於可以蒐集與/或操控大量的網路交通訊息。
	* False Information Attack：VANET車輛運用其他車輛或RSU生產生或傳遞的資料。這些接受/傳遞的資料不一定是真實的，攻擊者車輛可以產生假資料及傳送至VANET。一般假資訊攻擊包括
		* Fake Location Information：車輛可能廣未假位置資訊，這是一個嚴重問題因為與安全性相關的應用程式/系統依賴精確的車輛位置資料，假資料造成不正確的反應。同時，當封包傳遞至虛幻車輛(Phantom vehicles)時，假位置資訊將造成資料封包遺失。
		* Sensor Deception：藉由模擬假駕駛狀態，攻擊者可以欺騙車輛內的感測器，如在短不不斷地煞車，攻擊者可以模擬路上的交通壅塞，以及車輛可以不正確地廣播交通壅塞的訊息。
	* Replay Attack：訊息延後儲存及廣播致使欺騙網路其他節點。攻擊中，重播的訊息不再有用及真實。攻擊者的目的重製及利用原訊息傳送時的狀況藉由重復廣播被儲存的訊息。
	* Passive Eavesdropping Attack：監控網路以追蹤車輛移動或收聽他們的通訊。攻擊節點簡易地攔截及檢查網路中流動的訊息。攻擊者的目的是蒐集車輛及通訊模式的資訊以便作為未來攻擊

-----

[^1]: [女巫攻擊](https://academy.binance.com/zt/articles/sybil-attacks-explained)
[^2]: [橢圓曲線密碼學](https://zh.m.wikipedia.org/zh-tw/%E6%A4%AD%E5%9C%86%E6%9B%B2%E7%BA%BF%E5%AF%86%E7%A0%81%E5%AD%A6)


