---
date: 2024-01-03
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

下圖中 `File01-1.txt` 圖示有綠燈，代表有在 Depot 上。`File01-2.txt` 則只有在本地 Workspace 中

![2024-01-02 180254](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-02%20180254.png)

選取要新增的文件右鍵選擇 `Mark for Add`

![2024-01-03 120537](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20120537.png)

該文件會加到你選擇的 Pending Changelist，且多了一個紅色加號的圖示

![2024-01-03 120657](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20120657.png)
### 刪除文件（Mark for delete）
選取要刪除的文件右鍵選擇 `Mark for Delete`

![2024-01-03 114717](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20114717.png)

該文件會加到你選擇的 Pending Changelist，且多了一個紅色叉叉的圖示

![2024-01-03 115238](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20115238.png)
### 修改文件（Check out）
Perforce 會將有紀錄在 Depot 上文件改成唯讀，若想修改檔案必須先取得修改權（Check out）

選取要修改的文件右鍵選擇 `Check out`

![2024-01-03 121336](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20121336.png)

該文件會加到你選擇的 Pending Changelist，且多了一個紅色勾勾的圖示

![2024-01-03 121531](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20121531.png)
<br>
## 撤回未提交修改（Revert）
可以撤回在 Pending 的 Changelist 中的文件，撤回後文件會回到 Check out 前的版本

對著 Changelist 或文件右鍵選擇 `Revert Files`，也可選擇 `Revert Unchanged Files` 將未更動的文件撤回，將有更動的文件留在 Changelist

![2024-01-03 114014](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20114014.png)
<br>
## 退回先前版本
想要退回到先前的版本有兩種方式，一種是直接獲取先前的版本（Get Revision），通常是確定某個版本的文件是想退回的版本時使用；另一種是復原版本（Undo Change），通常是確定某次版本修改了什麼而想要復原其動作時使用，兩種方式結果相同，只是使用的情境不一樣
### 獲取指定版本（Get Revision）
選取想獲取指定版本的文件右鍵選擇 `Get Revision`

![2024-01-03 184728](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20184728.png)

選擇想要退回的版本號後點擊 Get Revision

![2024-01-03 185004](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20185004.png)

會看到檔案旁邊出現黃色驚嘆號，代表因為現在 Workspace 的文件退回到舊的版本，所以和 Depot 上最新版不一致。接著，選取該檔案右鍵選擇 `Check out`

![2024-01-03 185412](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20185412.png)

`Check out` 後會跳出一個視窗，點擊 `Don't Get Latest`

![2024-01-03 191341](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20191341.png)

此時要 Submit Changelist 時會跳出版本不是最新版的警告

![2024-01-03 191618](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20191618.png)

回到 Pending 頁面選取該文件右鍵選擇 `Get Latest Revision`

![2024-01-03 191501](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20191501.png)

接著會跳出紅色問號的圖示，解決方法見 [[#版本衝突（Resolve）]]

![2024-01-03 191918](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20191918.png)

版本衝突解決完後，就可以 Submit 了

### 復原版本（Undo Change）
到 History 頁面，選取想復原的版本右鍵選擇 `Undo Changes in Changelist XX`

![2024-01-04 114422](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-04%20114422.png)

跳出視窗並點擊 Save to Changelist

![2024-01-04 122254](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-04%20122254.png)

該版本裡所有的檔案再將該版本 Submit

![2024-01-04 120411](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-04%20120411.png)

若不想復原整個版本而是特定的檔案，直接選取該檔案右鍵選擇 `Undo Changes`

![2024-01-04 140332](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-04%20140332.png)

再選擇想復原的條件後點擊 Save to Changelist

![2024-01-04 141404](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-04%20141404.png)
<br>

## 版本衝突（Resolve）
選取有版本衝突的文件右鍵選擇 `Resolve`

![2024-01-03 192329](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20192329.png)

接著會跳出一個視窗，視窗左邊代表文件在 Workspace 的版本，右邊代表文件在 Depot 的最新版本

![2024-01-03 192517](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20192517.png)

視窗下方有幾個選項，`Accept Source` 代表選擇 Depot 上的版本，`Accept Target` 代表選擇 Workspace 上的版本，點擊其中一個後版本衝突就解決了

![2024-01-03 192802](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-03%20192802.png)

<br>

## 版本檢查（Reconcile Offline Work）
有時會忘記對某些文件 `Check out`、`Mark for add`、`Mark for delete`，或 Perforce 出問題導致 Workspace 與 Depot 上文件版本不一致

`Reconile Offline Work` 能很好的解決這問題，該功能能比較 Workspace 和 Depot 目錄中版本不一樣的文件，且可以自動將沒有 `Check out`、`Mark for add`、`Mark for delete` 的文件列出來

選取想檢查的資料夾右鍵選擇 `Reconcile Offline Work`

![2024-01-04 141950](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-04%20141950.png)

若有找到沒追蹤的檔案會跳出一個視窗，將需要 Reconcile 的文件勾選起來後點擊 Reconcile

![2024-01-04 142731](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-04%20142731.png)

檔案就會被加到 Changelist 中

![2024-01-04 143136](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2024-01-04%20143136.png)
<br>
## 版本擱置（Shelves）
當有些版本在本地已經修改了，但想讓別人獲取或是自己暫存，卻不想進版時可以使用 `Shelves`。被擱置的版本會上傳到伺服器上但是不會進版，別人或自己可以在從伺服器上拉下來