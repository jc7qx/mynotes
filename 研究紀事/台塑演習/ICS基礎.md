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
* 「Energetic Bear」駭客組織攻擊