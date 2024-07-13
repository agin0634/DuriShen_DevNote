---
date: 2024-07-04
tags:
  - UE5
  - Animation
  - Optimization
---
---
>AnimTotexture Plugin 允許建立動畫靜態網格物體，其外觀和行為類似於骨架網格物體。這在效能最佳化方面尤其重要，因為與靜態網格物件不同，計算和渲染骨架網格物件的動畫對效能要求極高

<br>
開啟 AnimToTexture Plugin

找到想轉換的 Skeletal Mesh，點擊 `Make Static Mesh` 創建一個新的 Static Mesh

![screenshot 2024-07-13 at 11.54.51 AM|500](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2011.54.51%20AM.jpg)

創建新的 `Anim to Texture Data Asset`

![screenshot 2024-07-13 at 11.56.57 AM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2011.56.57%20AM.jpg)

設定好 Skeletal Mesh 和 Static Mesh，要注意的是 UVChannel，若 Channel 已被 LightMap 占用則無法使用，後面會提到

![screenshot 2024-07-13 at 11.58.24 AM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2011.58.24%20AM.jpg)

設定了動畫資料的儲存方式。 `Enforce Power Of Two` 不是必要的，但它有助於使動畫播放更流暢，且更好地利用紋理壓縮

Mode 中可以選擇 `Bone` 或 `Vertex`。 Bone 是更輕量的選項，因為各個骨骼的位置和影響並不嚴格依賴頂點 ID。這意味著大部分烘焙數據可以在任何類似比例的角色或網格及其所有 LOD 上重複使用。不過，每個單獨的靜態網格物件或 LOD 確實需要自己的骨骼權重紋理。使用 Bone 的另一個好處是產生的紋理的總記憶體佔用會更低，因為要追蹤的骨骼數量低於網格中的頂點數量

