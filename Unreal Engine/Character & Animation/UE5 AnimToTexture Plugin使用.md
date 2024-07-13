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

![screenshot 2024-07-13 at 12.00.47 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2012.00.47%20PM.jpg)

創建一個 Render Target，再依照需要的貼圖數量創建點擊右鍵選擇 `Create Static Texture`

![screenshot 2024-07-13 at 12.01.53 PM|500](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2012.01.53%20PM.jpg)

設定要烘焙的動畫

![screenshot 2024-07-13 at 12.02.41 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2012.02.41%20PM.jpg)

將模型的材質球修改成這樣，可直接複製 Plugins 中的
- Bone Animation
  ![screenshot 2024-07-13 at 12.04.10 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2012.04.10%20PM.jpg)
- Vertex Animation
  ![screenshot 2024-07-13 at 12.05.09 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2012.05.09%20PM.jpg)

並創建 Material Instance

![screenshot 2024-07-13 at 12.06.06 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2012.06.06%20PM.jpg)

在 Plugins>AnimToTexture Content>Characters>Mannequin 下會看到轉換用的 Blueprint (BP_AnimToTexture)

依照選擇的模式改線，`BoneDataAsset` 替換成剛創建的 DA。上面有提到被 LightMap 占用的 Channel 無法覆寫，所以我們將 LightMap Channel 移至 Channel2，但要注意 LightMap Channel 改變可能會影響其他使用的地方

![screenshot 2024-07-13 at 12.07.45 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2012.07.45%20PM.jpg)

UVChannel 已被 LightMap 使用

![screenshot 2024-07-13 at 12.08.21 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2012.08.21%20PM.jpg)

替換 `Update Material Instance from Data Asset` 中的 Material Instance 成剛創建的 Material Instance

![screenshot 2024-07-13 at 12.09.10 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-07-13%20at%2012.09.10%20PM.jpg)

