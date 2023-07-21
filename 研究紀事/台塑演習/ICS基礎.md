ICS由IT系統組成用於控制工業製程(industrial process)，系統組成可能包括SCADA，DCS，PLC...。一些實際的ICS資通攻擊實例，如Stuxnet, Flame, Duqu, Gauss, Shamoon, Havex...等。
![[Pasted image 20230721120557.png]]![[Pasted image 20230721120612.png]]
![[Pasted image 20230721120948.png]]

ICS與IT的資安防護理念
IT -> Confidentiality, Integrity, Availability
ICS (Lower-Level) -> Safety, Availability, Integrity, Confidentiality
ICS (Higer-Level) -> Safety, Integrity, Availability, Confidentiality

Defense-in-Depth Model
* system (include Policies & procedures)
* system design
* network design
* romote access
* physical protection
![[Pasted image 20230721121700.png]]
ICS資通攻擊行動
* 直接攻擊ICS裝備
	* 利用裝置的弱點
	* 影響有限
* 阻絕服務/阻絕控制
	* 有限的知識及資源即可
	* 不太會造成災難性影響
* 複雜流程攻擊
	* 集合ICS、流程、資通安全知識
	* 複雜及持續攻擊
	* 可能造成災難性衝擊

ICS攻擊模式
* Loss of View (LoV)
* Manipulation of View (MoV)
* Denial of Control (DoC)
* Manipulation of Control (MoC)
* Loss of Control (LoC)

攻擊流程
* Surveillance
* System Mapping
* Initial Infection & Compromise
* Information Exfiltration
* Preparing the Final Attack
* Testing Incident Detection & Response
* Launch the Attack

Stuxnet
* 成功的複雜攻擊
* 2010年
* 2005被發現
* 目標為伊朗核子工廠
* 由受感染拇指碟執行
* 煉製濃縮柚離心機的頻率
* 攻擊電腦及PLC

Havex
* 遠端存取木馬(RAT=Remote Access Trojan)
	* watering hole attack
	* 使用ICS維修商遞送RAT
	* 更換合法的軟體裝置程式
	* 內藏惡意碼的軟體裝置程式造成C&C系統後門
* 「Energetic Bear」駭客組織攻擊能源領域
* 蒐集有關OPC傳統伺服器資訊，而非POC-UA
* 利用DCOM找出可能的網路上伺服器
* Capable of Enumerating OPC Tags
* ICS-CERT測試顯示伺服器毀損
* 資源包括ICS-CERT, Symantec, CrowdStrike, F-Secure, FireEye, DigitalBond

想定
1. 電力產生過程使渦輪超速，利用仿造ICS資通安全研究公司發出的垃圾釣魚郵件
2. 阿摩尼亞工廠爆炸，心懷不滿的員工在製程中操控加熱，關閉警示及安全系統，增加甲烷化中的一氧化碳
	* 員工因故被解職
3. 鍋爐爆炸，停止輸送冷卻水，使溫度升高。由白帽研究者利用武器化的
	* 白帽駭客發現弱點，開發概念證明
	* 將概念證明供諸大眾
	* 黑帽駭客利用武器攻擊
	* 針對特定裝置搜索攻擊的程式
	* 攻擊者將感染的USB拇指碟丟在工廠外
	* 建立C&C中心，蒐集資訊，選擇目標
	* 根據可能衝擊決定攻擊目標
	* 特定日期/時間發送攻擊指令

