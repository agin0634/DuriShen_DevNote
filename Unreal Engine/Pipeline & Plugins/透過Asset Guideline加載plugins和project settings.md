---
date: 2023-08-01
tags:
  - UE4
  - UE5
  - Editor
  - Blueprint
  - Asset
Version: UE5.1
---
---
> 透過附加在 Asset 上的 User data 來檢查 guidlelines (plugins, project settings, etc) 是否加載

<br>

準備一個 Static Mesh，找到 General Settings>Asset User Data，新增一個 Asset Guideline，並填上想附加的 Plugin。填入 Guideline Name 並注意名字不能重複

![2023-08-01 222206](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-08-01%20222206.png)

Project Settings 也同理

![2023-08-01 222331](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-08-01%20222331.png)

使用 `Async Load Asset` 來載入 Asset

![2023-08-01 222345](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-08-01%20222345.png)

載入 Asset 時，右下角會跳出警告視窗，會看到 Needed Plugins 下列出剛剛填入的 Plugin，並點擊 `Enable Missing`

![2023-08-01 222357](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-08-01%20222357.png)

接著會再跳出一個視窗，點擊 `Restart Now`，編輯器會重啟。重啟後 Plugins 或 Project Settings 的改動就會被啟用了

![2023-08-01 222408](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-08-01%20222408.png)

<br>

## Ref
[UAssetGuideline | Unreal Engine Documentation](https://docs.unrealengine.com/4.26/en-US/API/Editor/UnrealEd/Editor/UAssetGuideline/)