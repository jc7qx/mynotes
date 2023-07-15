unity中每一個物件都有一個Transform類別，用來儲存及操作物件的位置、旋轉、及縮放的資料。
`trnsform.position` 表示物件的位置 (x, y, z)
`transform.rotation` 表示物件的旋轉姿態 (x_angle, y_angle, z_angle)針對每個軸的旋轉角度，角度定義時須使用 `Quaternion.eulerAngles` 格式
* `transform.rotation = Quaternion.Euler(new Vector3(20.0f, -30.0f, 50.0f));`
* `transform.Rotate(20f, -30f, 50f);`
`Translate` 物件依據方向與距離（向量）來移動

`Quaternion.identity`  ( READ ONLY) : 毫無旋轉，回歸原始旋轉值，簡單來說就 rotation(0,0,0)

`GetComponent<Transform>( ).LookAt(target)` 使物件朝向目標的方向

 [Unity3d how to have a "text label" follow a game object](https://stackoverflow.com/questions/70756743/unity3d-how-to-have-a-text-label-follow-a-game-object)



#uniyt #movement




