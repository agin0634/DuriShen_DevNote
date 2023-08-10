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

新增一個 float 的變數 `TickRatePerSecond`，並把 `Set Timer by Function Name` 節點的 Looping 啟用、Function Name 填入 `EditorTick`
![2023-08-10 223246](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-08-10%20223246.png)