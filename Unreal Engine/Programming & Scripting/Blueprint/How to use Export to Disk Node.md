---
date: 2024-07-16
tags:
  - UE5
  - Blueprint
  - Blueprint-Node
  - Texture
Version: UE5.3
---
---
## 節點
`Filename` 可以指定存檔路徑，若沒指定會存在引擎資料夾下
```
\Epic Games\UE_5.3\Engine\Binaries\Win64
```

![screenshot 2024-07-20 at 2.15.10 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-07-20%20at%202.15.10%20PM.jpg)

使用`Options on Complete` delegate 時會發現從節點生成的 event 會報錯

![screenshot 2024-07-20 at 2.16.01 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-07-20%20at%202.16.01%20PM.jpg)

自行創建一個 CustomEvent 並加上一個 Boolean 的 output 就解決了

![screenshot 2024-07-20 at 2.16.46 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-07-20%20at%202.16.46%20PM.jpg)

<br>

## 輸出 Texture
輸出 Textrue 時出現不知援圖檔格式的報錯

![screenshot 2024-07-20 at 2.17.33 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-07-20%20at%202.17.33%20PM.jpg)

將 Texture Compression Settings 改成 `UserInterface2D` 即可解決

![screenshot 2024-07-20 at 2.18.05 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-07-20%20at%202.18.05%20PM.jpg)

<br>

## 輸出 Render Target
Render Target 預設的格式 `RGBA16f` 只有支援 EXR 格式，若要輸出 PNG 格式，將 Render Target Format 改成 `RGBA8 SRGB`

![screenshot 2024-07-20 at 2.18.50 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-07-20%20at%202.18.50%20PM.jpg)

並找到 SceneCapture2D 下的 Capture Source 改成 `SceneDepth in A` 或其他有輸出 alpha 的選項

![screenshot 2024-07-20 at 2.19.57 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-07-20%20at%202.19.57%20PM.jpg)