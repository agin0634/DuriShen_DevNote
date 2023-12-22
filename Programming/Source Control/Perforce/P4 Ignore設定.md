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
p4 set P4IGNORE=.p4ignore
```
- 優點：過濾文件可以放在硬碟任意位置
- 缺點：只能指定一個過濾文件

**文件名指定**
```
p4 set P4IGNORE=.p4ignore
```
- 優點：可指定多ㄜ
- 缺點：過濾文件只能放在 Workspace 路徑中
<br>


## Ignore 文件編輯