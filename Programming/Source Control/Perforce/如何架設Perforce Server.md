---
date: 2023-12-21
tags:
  - SourceControl
  - Perforce
---
---
## 安裝 P4D
**Step.1 安裝 Helix Server(P4D)**
在 [Download Helix Core (P4D) | Perforce](https://www.perforce.com/downloads/helix-core-p4d) 選擇平台並下載

**Step.2 安裝設定**
開啟剛下載好的 helix-core-server-x64.exe。這邊照著預設即可，直接點擊 Next

![2023-12-26 120146](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2023-12-26%20120146.png)

設定 Server IP， Port 基本上預設的 1666 即可，接著在設定 Server 要存放資料的路徑 

![2023-12-26 115248](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2023-12-26%20115248.png)

接著點擊 Start 開始安裝

**Step.3 防火牆設定**
在控制台>系統及安全性>Windows Defender 左側欄位找到**進階設定**

![2023-12-21 182528](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2023-12-21%20182528.png)

新增一個新增一個輸入規則，選擇連接埠後，下一步

![2023-12-21 195558](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2023-12-21%20195558.png)

上面選擇 TCP 、下面選擇特定連接埠：並輸入安裝時的 Port，再來點擊下一步

![2023-12-21 184629](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2023-12-21%20184629.png)

動作和設定檔設定完成後填上規則的名字

![2023-12-21 185601](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2023-12-21%20185601.png)

## 安裝 P4V 和 P4Admin
**Step.1 安裝P4V**
在[Download Helix Visual Client (P4V) | Perforce](https://www.perforce.com/downloads/helix-visual-client-p4v)選擇平台並下載

**Step.2 安裝設定**
開啟剛下載好的 p4vinst64.exe。這邊照著預設即可，直接點擊 Next

![2023-12-26 1254559](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2023-12-26%201254559.png)

安裝成功後就能開始使用了，操作詳見：
- [[P4admin常見操作]]
- [[PV4常見操作]]
