---
date: 2023-12-21
tags:
  - SourceControl
  - Perforce
---
---
**Step.1 安裝 Helix Server(P4D)**
在 [Download Helix Core (P4D) | Perforce](https://www.perforce.com/downloads/helix-core-p4d) 選擇平台並下載

**Step.2 安裝設定**
開啟剛下載好的 helix-core-server-x64.exe。這邊照著預設即可，直接點擊 Next
![2023-12-21 180926](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-12-21%20180926.png)

設定 Server IP， Port 基本上預設的 1666 即可
![2023-12-21 181241](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-12-21%20181241.png)

接著點擊 Start 開始安裝

**Step.3 防火牆設定**
在控制台>系統及安全性>Windows Defender 左側欄位找到**進階設定**
![2023-12-21 182528](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-12-21%20182528.png)

新增一個新增一個輸入規則，
![2023-12-21 195558](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-12-21%20195558.png)