---
date : 2023-07-29
tags : UE4 UE5 Shader
---
---
![2023_07_29_18_37_00_828](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023_07_29_18_37_00_828.gif)
<br>

## MPC
創建一個新的 MPC，並新增2個 Vector Parameters: `Position` 和 `Normal`
![2023-07-29-181651](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-07-29-181651.png)

<br>

## Blueprint
創建一個新的 BP，並新增一個 Plane Mesh Component 做為切割面的預覽，再取得 Plane 的 `World Position` 和 `Up Vector`，並分別接上剛創建的 MPC 的 `Position` 和 `Normal`
![2023-07-29 182435](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-07-29%20182435.png)

<br>

## Material
創建一個新的 Material，Blend Mode 改成 `Masked` 、Two Sided 為 `True`，並按照下圖串接節點，Bace Color 可接上任何顏色或貼圖
![2023-07-29 183320](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-07-29%20183320.png)

將材質球套上想切的模型，並透過剛創建的 Blueprint 改變裁切位置
![2023_07_29_18_37_00_828](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023_07_29_18_37_00_828.gif)