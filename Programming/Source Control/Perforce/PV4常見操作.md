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
`RnD_One_Depot`（綠勾） 代表映射了整個 Depot，而在 RnD_One_Depot 下的 `Folder01`（黑勾）則默認有映射；`Folder02`（紅叉）則取消映射；`Folder03`（綠勾）也是有映射的，效果等同黑勾。
`RnD_Two_Depot`（紅叉）則是取消映射整個 Depot

![2024-01-02 164749](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20164749.png)

值得注意的是 `Folder03` 雖然有映射，但右方 Client 端路徑錯了，不確定是否是 bug，但可以手動覆寫，雙擊路徑即可修改

![2024-01-02 171518](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20171518.png)

<br>

## 編輯 Workspace 中文件
在 Workspace 環境下對於任何文件的編輯，都須透過這3動作完成，否則將不會紀錄在 Changelist 中，因此會造成 Workspace 和 Depot 上檔案不同步
### 新增文件（Mark for add）
用於新增
### 刪除文件（Mark for delete）
### 修改文件（Checkout）