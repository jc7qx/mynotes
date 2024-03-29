# 遊戲實作練習B

## 遊戲名稱：射擊得分

### 遊戲描述

遊戲場設置紅、綠敵人與黃金寶物，玩家可以射擊怪物，搶奪寶物完成任務。遊戲一開始紅怪隨機位置生成，玩家搜尋紅怪射擊，紅怪被射擊3次，產生爆破效應及音效，並遭摧毀。此時，綠怪、黃金寶物隨機位置生成，綠怪開始追殺玩家，玩家躲避綠怪追捕搶奪黃金。玩家搶到黃金，進入場景2，任務完成，綠怪追到玩家，進入場景3，任務失敗。

### 遊戲設計

- 遊戲場規格：cube(名稱：floor)，大小為 20x20或更大，自選地板紋理，遊戲場周圍設置圍籬，防止物件掉落。
- 玩家設計：玩家有二種可能
    - 坦克
        - 坦克包含底盤，砲塔，砲管，及砲口
    - FPS，第一人稱主角
        - 由standard asset導入，設定武器及準星
    - Camera跟隨在player後上方跟拍，player頭上訊息顯示
    - 玩家可以運動及射擊
        - 坦克射擊武器為砲彈
        - FPS射擊武器為鐳射光
- 砲彈製作：
    - 砲彈為預製物（prefab）
    - 射擊方式為按下Space鍵瞬間，在player正前方射出砲彈，砲彈施加外力才能運動
    - 砲彈可以偵測擊中的目標，紀錄目標被擊中數量，以及擊中目標後字型摧毀
    - 砲彈射程有限
- 鐳射光武器設計：
    - 雷射武器使用raycast方法製作
    - 需要製作雷射槍管及準星
    - 雷射武器射程有限
- 目標設計：
    - 紅怪
        - 遊戲一開始出現在場景中的隨機位置
        - 紅怪被擊中時會被武器推動，被擊中3次後，產生爆炸效應及音效，隨即自行摧毀
    - 綠怪
        - 紅怪被擊毀後，綠怪隨機位置生成在場景中
        - 綠怪開始追捕玩家
        - 綠怪追捕到玩家進入失敗場景
    - 黃金寶物
        - 紅怪被擊毀後，黃金隨機位置生成在場景中
        - 玩家搶到黃金進入勝利場景
- 場景設計
    - 主場景 scene1
    - 勝利場景 scene2
        - 光線漸暗、光線亮滅、字型顏色漸變
    - 失敗場景 scene3
        - 光線漸暗、光線亮滅、字型顏色漸變
- 訊息設計：
    - 訊息欄顯示在玩家頭頂，第一行為遊戲訊息，第二行為學號姓名
    - 訊息內容與遊戲狀態相關
        - `gameStatus` = 1, “尋找目標射擊紅怪”
        - `gameStatus` = 2, “躲避追捕搶奪黃金”
        - `gameStatus` = 3, “完成任務”
        - `gameStatus` = 4, “任務失敗”

### 遊戲開發

- 建立玩家
    1. 坦克
        - 3D model
        - 坦克移動控制 moving.cs
        - 坦克射擊控制 firing.cs
            - 砲彈預置物件 projectile.cs
            - 射出位置
            - 射擊參數
    2. FPS
        - 第一人稱角色導入
        - 武器安裝與設定
        - 雷射武器發射與命中 raygun.cs
- 敵人與黃金
    - 隨機出現 randPos.cs
    - 紅怪 damage.cs
        - 被擊中效果
            - 音效
            - 爆炸粒子系統
    - 綠怪 capture.cs
        - 追捕玩家
    - 黃金 getGold.cs
- 遊戲控制 GameManager.cs
- 場景轉換
    - 場景管理與呼叫
    - scene1 主場景
    - scene2 失敗場景
        - 光線變化 flicker.cs, darking.cs
    - scene3 勝利場景
        - 訊息變色 colorchange.cs
- 輔助訊息顯示 showMessage.cs
    - 建立訊息框
    - 訊息顯示

### 遊戲程式

射擊程式

```csharp
// Fire.cs

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class firing : MonoBehaviour
{
    public GameObject bombPrefab;

    // Update is called once per frame
    void Update()
    {
        if (Input.GetKeyDown(KeyCode.F))
        {
            GameObject b = Instantiate(bombPrefab, transform.position+transform.forward, transform.rotation);
            b.GetComponent<Rigidbody>().velocity = transform.forward*30;
            Destroy(b, 5f);
        }
    }
}
```

遊戲主控程式

```csharp
// GameManager.cs，嵌入一個空物件中

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class GameManager : MonoBehaviour
{
    public static int redCount, greenCount, blueCount;
    // Start is called before the first frame update
    void Start()
    {
        redCount = 0;
	greenCount = 0;
	blueCount = 0;
    }
}
```

訊息顯示程式

```csharp
// Messager.cs

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;

public class showmessage : MonoBehaviour
{
    // Update is called once per frame
    void Update()
    {
        GetComponent<Text>().text = “學號-姓名” + "Red: " + GameManager.redCount + 
        " Green: " +GameManager.greenCount + " Blue: " + GameManager.blueCount;
    }
}
```

命中標靶程式

```csharp
// BombImpact.cs

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class RedImpact : MonoBehaviour
{
    private void OnCollisionEnter(Collision other)
    {
        if (other.gameObject.CompareTag("BB"))
        {
            GameManager.redCount++;
        }
    }
}
```