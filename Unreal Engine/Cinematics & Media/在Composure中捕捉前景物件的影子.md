---
date: 2024-07-05
tags:
  - UE5
  - Composure
  - AR
  - Shadow
  - Compositing
---
---
準備好要做為前景合成的物件和一台攝影機

![screenshot 2024-07-06 at 2.24.14 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.24.14%20PM.jpg)

放置任何模型到場景中作為被影子照射的物體，可以照合成的背景的結構調整

![screenshot 2024-07-06 at 2.25.49 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.25.49%20PM.jpg)

創建兩個 Layer，前景的模型放入`FG`，被影子照射的物體放入 `ShadowCatcher`

![screenshot 2024-07-06 at 2.28.04 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.28.04%20PM.jpg)

創建一個新的 Comp，再創建一個 Media Layer 和三個 CG Layer
- Media: 合成的背景
- FG: 前景要合成的主體
- Shadow: 前景和被前景影子照射的物體
- ShadowCatcher: 被前景影子照射的物體


