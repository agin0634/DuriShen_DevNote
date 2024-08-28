---
date: 2024-08-24
tags:
  - UE5
  - XR
  - MetaXR
  - Hand-Tracking
  - Oculus-Quest
  - Quest-Link
Version: UE5.4
---
---
## 安裝 Plugin
到 Meta 官網下載 Meta XR Plugin
 [Downloads - Unreal Engine 5 Integration (oculus.com)](https://developer.oculus.com/downloads/package/unreal-engine-5-integration/)

將檔案解壓縮到引擎安裝路徑
```
..\Engine\Plugins\Marketplace
```

開啟專案檔後啟用 Plugin

![screenshot 2024-08-27 at 6.26.39 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-27%20at%206.26.39%20PM.jpg)
<br>
## 環境設定
若要透過 Quest Link 在 PCVR 中使用 hand tracking 功能，要先在 Meta Quest Link app 中開啟`開發人員執行期間功能`

![screenshot 2024-08-27 at 6.29.15 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-27%20at%206.29.15%20PM.jpg)

在 Unreal 專案中找到 Project Setiings>MetaXR>Mobile>Hand Tracking Support，將選項改成 C`ontrollers and Hands` 或 `Hands Only`

![screenshot 2024-08-27 at 6.30.11 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-27%20at%206.30.11%20PM.jpg)
<br>
## Pawn
創建一個 Pawn ，創建左右手的 `MotionControllerComponent` 及 `OculusXRHandComponent`

![screenshot 2024-08-28 at 12.05.49 PM | 500](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-28%20at%2012.05.49%20PM.jpg)

將 OculusXRHand 下的 `Skeleton Type` 和 `Mesh Type` 改成對應的手

![screenshot 2024-08-28 at 12.07.09 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-28%20at%2012.07.09%20PM.jpg)

進遊戲後就會看到預設的手，不須額外套模型

![screenshot 2024-08-28 at 12.07.51 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-28%20at%2012.07.51%20PM.jpg)