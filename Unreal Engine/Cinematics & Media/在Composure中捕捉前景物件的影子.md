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

![screenshot 2024-07-06 at 2.29.22 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.29.22%20PM.jpg)

設定好 Comp 攝影機

![screenshot 2024-07-06 at 2.30.24 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.30.24%20PM.jpg)

創建一個新的 Material

![screenshot 2024-07-06 at 2.31.37 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.31.37%20PM.jpg)

放入 Comp 的 Transform Pass，並按照名字設定好 Input Elements

![screenshot 2024-07-06 at 2.32.37 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.32.37%20PM.jpg)

到 `FG` CG Layer 設定 Input Captrue Actors 為 `FG Layer`

![screenshot 2024-07-06 at 2.35.24 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.35.24%20PM.jpg)

`Shadow` CG Layer 設定 Input Captrue Actors 為 `FG Layer` 和 `ShadowCatcher Layer`

![screenshot 2024-07-06 at 2.37.08 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.37.08%20PM.jpg)

`ShadowCatcher` CG Layer 設定 Input Captrue Actors 為 `ShadowCatcher Layer`

![screenshot 2024-07-06 at 2.38.37 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.38.37%20PM.jpg)

回到 Comp 點開 Preview 就會看到合成結果

![screenshot 2024-07-06 at 2.39.36 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-06%20at%202.39.36%20PM.jpg)

調整攝影機角度和燈光就完成了



