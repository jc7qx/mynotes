1. 遊戲流程
	* 紅怪隨機位置生成
	* 玩家搜尋紅怪射擊
	* 紅怪被射擊3次，產生爆破效應及音效，摧毀
	* 綠怪、黃金隨機位置生成
	* 玩家躲避綠怪追捕搶奪黃金
	* 玩家搶到黃金，進入場景2，任務完成
	* 綠怪追到玩家，進入場景3，任務失敗
1. 建立遊戲場
	* 地板(floor)、圍籬(walls)
2. 建立坦克模型
	* 坦克主體、砲口
	* firing.cs
	* moving.cs
3. 建立怪物、黃金模型
	* 紅怪
		* takeDamage.cs
	* 綠怪
		* capture.cs
	* 黃金
		* getGold.cs
	* randPos.cs
4. 建立砲彈預製模型
	* projectile.cs
5. 遊戲控制
	* GameManager.cs
	* showMSG.cs
6. 場景燈光控制
	* flicker.cs
7. 字型顏色控制
	* colorGradient.
建立FPS