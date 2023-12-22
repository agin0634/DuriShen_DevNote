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
![2023-12-22 180340](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-12-22%20180340.png)

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