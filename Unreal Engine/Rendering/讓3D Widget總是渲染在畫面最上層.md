---
date: 2023-08-24
tags:
  - UE4
  - UE5
  - Shader
  - Widget
Version: UE5.1
---
---
> 使用 3D Widget 時會遇到被場景中物件遮擋的問題(左圖)，只需簡單的調整材質球設定就可以讓 3D Widget 總是渲染在畫面最上層(右圖)

![20230824_15452154](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/20230824_15452154.jpg)

<br>

找到 Widget 的材質球

![20230824_3257485315](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/20230824_3257485315.png)

將材質球的 Blend Mode 改為 `Translucent`，並將 Translucency>Disable Depth Test 改為 `True`

![20230824_2478465245](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/20230824_2478465245.png)