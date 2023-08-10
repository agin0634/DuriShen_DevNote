---
date : 2023-08-10
tags : UE4 UE5 Editor Blueprint
---
Status::🌱
---
創建一個類別為 `EditorUtilityBlueprint` 的 Blueprint
![2023-08-10 215357](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-08-10%20215357.png)

開啟BP並在 `Class Default` 更改以下設定
```
Allow Tick Before Begin Play = True
Tick Even When Paused = True
Is Editor Only Actor = True
```