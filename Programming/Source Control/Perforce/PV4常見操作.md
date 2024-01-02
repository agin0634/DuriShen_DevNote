---
date: 2024-01-02
tags:
  - SourceControl
  - Perforce
---
---
## 創建新 Workspace
不管目標的 Depot 類型是哪種，Client 端都需要創建 Workspace 才能讀或寫 Depot 上的文件 
 - Depot: Server端的目錄
 - Workspace: Client端的目錄

在 Workspace 頁面點擊 New Workspace

![2024-01-02 151441](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20151441.png)

填入 `Workspace name` 和 `Workspace root`
> 建議將所有 Workspace root 集中在一個目錄（綠底線），在 root 中創建一個和 Workspace name 一樣的資料夾（紅底線）


![2024-01-02 155316](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20155316.png)

映射 Workspace 目錄，點選 Depot 或 Folder 後點擊下方按鈕進行映射
- ![p4v-button-include-mapping_27x15](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/p4v-button-include-mapping_27x15.webp) Include
- ![p4v-button-exclude-mapping_27x15](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/p4v-button-exclude-mapping_27x15.webp) Exclude
- ![p4v-button-clear-mapping_25x15](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/p4v-button-clear-mapping_25x15.webp) Clear

以下圖為例：
`RnD_One_Depot`（綠勾） 代表我有映射整個 Depot，而在 RnD_One_Depot 下的 `Folder01`（黑勾）則默認有映射；`Folder02`（紅叉）則取消映射；`Folder03`（綠勾）也是有映射的，效果等同黑勾，但映射路徑是錯的

![2024-01-02 164749](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20164749.png)