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

點擊 Advanced 頁面，將 `Rmdir` 打勾；`On submit` 改成 `Don't submit unchanged files`（依照使用習慣）

![2024-01-02 182106](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20182106.png)
<br>

## 獲取版本（Get Revision）
若文件旁出現黃色驚嘆號圖示，代表 Workspace 與 Depot 文件版本不一致

![2024-01-02 185002](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20185002.png)

選取資料夾或文件右鍵選擇 `Get Latest Revision` 來抓取 Depot 上的最新版本

![2024-01-02 191119](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20191119.png)

或選擇 `Get Revision` 來指定抓取的版本，一般用於退回某個版本

![2024-01-02 191415](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20191415.png)

有時因為 Perforce 出現問題或操作不當導致文件沒更新，可勾選下方 `Force Operation` ，這樣會強制獲取 Depot 上的版本覆蓋 Workspace 的版本

![2024-01-02 191847](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20191847.png)

> [!warning] 提交版本或是編輯文件前，請記得先獲取最新版本

<br>

## 提交版本（Submit）
Perforce 提交是以 Changelist 為單位，修改過的文件會紀錄在一個 Changelist 中，而一個 Changelist 可以看作為一個版本

尚未提交的 Changelist 會先存放在 Pending 的頁面中

![2024-01-02 192940](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20192940.png)

選取要提交的 Changelist 右鍵選擇 `Submit`

![2024-01-02 193619](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20193619.png)

填入備註後再點擊 `Submit`

![2024-01-02 193848](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20193848.png)

提交成功後即可在 History 頁面看到剛提交的版本

![2024-01-02 194100](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20194100.png)
<br>

## 編輯 Workspace 文件
在 Workspace 環境下對於任何文件的編輯，都須透過這3動作完成，否則將不會紀錄在 Changelist 中，因此會造成 Workspace 和 Depot 上檔案不同步
### 新增文件（Mark for add）
新增 Depot 上沒有的文件

下圖中 `File01-1.txt` 圖示有綠燈，代表有在 Depot 上

![2024-01-02 180254](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20180254.png)

啊啊

### 刪除文件（Mark for delete）
刪除 Depot 上的文件
### 修改文件（Checkout）
hdkjlkd
<br>
## 撤回未提交修改（Revert）
dkwjdkwejdklew

<br>
## 退回先前版本
### 獲取指定版本（Get Revision）
### 復原版本（Undo Change）


