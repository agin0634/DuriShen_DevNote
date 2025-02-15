---
date: 2023-12-23
tags:
  - SourceControl
  - Perforce
---
---
## 指定.p4ignore
開啟 CMD 輸入:

**絕對路徑指定**
```
p4 set P4IGNORE=C:\myP4Setting\.p4ignore
```
- 優點：過濾文件可以放在硬碟任意位置
- 缺點：只能指定一個過濾文件


**文件名指定**
```
p4 set P4IGNORE=.p4ignore
```
在 Workspace root 資料夾下的所有名字符合的過濾文件都會起作用
- 優點：可指定多個過濾文件
- 缺點：過濾文件只能放在 Workspace 路徑中


若想確認是否指定成功，再輸入
```
p4 set
```
![2023-12-22 180340](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2023-12-22%20180340.png)

<br>

## 創建 Ignore 文件
若是使用 `文件名指定` 的方式，在 Workspace Root 資料夾下任一路徑點擊右鍵，在點選 Show in Explorer

![2024-01-02 142941](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2024-01-02%20142941.png)

創建一個新的文字文件 `.p4ignore`

![2024-01-02 143351](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2024-01-02%20143351.png)

編輯 Ignore 文件
**Unreal Engine Ignore File Example:**
```
# User-specific folders or temporary files that should not be versioned.
    Saved/
    Intermediate/
    DerivedDataCache/
    FileOpenOrder/
    obj/
# Certain file types that should not be versioned.
    *.pdb
    *-Debug.*
# Visual Studio user settings files that should be ignored.
    .vs/
```

回到 P4V，點選在 Workspace 下的 .p4ignore，在點擊 Mark for add

![2024-01-02 143856](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2024-01-02%20143856.png)

在 Pending 頁面選到剛剛 add 的文件點擊右鍵點選 Submit

![2024-01-02 144159](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2024-01-02%20144159.png)

簡單描述後在點擊 Submit

![2024-01-02 144726](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2024-01-02%20144726.png)
<br>

## Ignore 文件編輯
- (#) 是註解
- (!) 是指定不被過濾
- (\*) 是通配符號

```
# Ignore this folder
Build/*
Saved/*
!Saved/SaveGames/*       # Don't ignore SaveGames folder in Saved folder

# Ignore this files
*.slo
*.lo
*.o
*.obj
```